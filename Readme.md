# Uganda Text-to-Speech (TTS) Models

**🔗 [Access Models on HuggingFace](https://huggingface.co/Uganda-lang)**

A comprehensive suite of Text-to-Speech (TTS) models for Ugandan languages, supporting **English, Luganda, Runyonkole, Tesso, and Acholi** with multiple speaker voices for each language.

---

## Table of Contents

- [Introduction](#introduction)
- [Model Architecture](#model-architecture)
- [Supported Languages & Voices](#supported-languages--voices)
- [Inference Example](#inference-examples)
- [Access & Usage](#access--usage)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [Citation](#citation)

---

## Introduction

This project introduces a groundbreaking collection of Text-to-Speech models specifically designed for Ugandan languages. These models represent a significant advancement in African language technology, addressing the critical gap in speech synthesis capabilities for Uganda's diverse linguistic landscape.

The Uganda TTS model family consists of fine-tuned versions of the **Orpheus 3B model**, each specialized for different Ugandan languages while maintaining quality speech synthesis capabilities. Each language model supports multiple distinct speaker voices, enabling versatile applications in education, accessibility, content creation, and digital preservation of Ugandan languages.

These models are designed to serve researchers, developers, educators, and content creators who need high-quality speech synthesis in Ugandan languages, contributing to the broader goal of digital language preservation and accessibility in Africa.

## Model Architecture

The Uganda TTS models utilize a sophisticated two-stage architecture:

1. **Audio Token Generation**: The models generate audio tokens based on the SNAC (Structured Neural Audio Codec) framework
2. **Fine-tuned Processing**: These audio tokens are then processed through specialized fine-tuned versions of the Orpheus 3B model, each optimized for specific Ugandan languages

This architecture enables efficient and high-quality speech synthesis while maintaining computational efficiency suitable for various deployment scenarios. More about the Orpheous Models [here](https://canopylabs.ai/releases/orpheus_can_speak_any_language)

---

## Supported Languages & Voices

### English
**Supported Voices**: Barbara, Mary, Jennifer, Jessica, Susan, James, Linda, Patricia, Elizabeth, Christopher

### Luganda
**Supported Voices**: Charles, Sandra, Christopher, Mark, Barbara, Michelle, Karen, James, Margaret, Daniel

### Runyonkole
**Supported Voices**: Michelle, James, Patricia, Mark, Elizabeth, Charles, Daniel, Barbara, Christopher, Linda

### Tesso
**Supported Voices**: Michelle, Barbara, Jessica, Christopher, James, Daniel, Charles, Mark

### Acholi
**Supported Voices**: James, Barbara, Michelle, Mark, Christopher

---

## Inference Examples

### English Inference Example

Below is an example of how to use the Uganda TTS English model for inference. For other languages, please visit the [HuggingFace repository](https://huggingface.co/USOAL) for the appropriate model names and instructions. Or check the Notebooks folder that shows the inference full code for each of the languages.

```python
from unsloth import FastLanguageModel
import torch

# Download the English multi-speaker model
model, tokenizer = FastLanguageModel.from_pretrained(
    model_name = "Uganda-lang/Orpheous-Eng-multi-speaker",
    max_seq_length=2048,  # Choose any for long context!
    dtype=None,           # Select None for auto detection
    load_in_4bit=True,    # Select True for 4bit which reduces memory usage
    token="[token]",      # Replace with your HuggingFace token
)
```

```python
# Download the SNAC model
from snac import SNAC

snac_model = SNAC.from_pretrained("hubertsiuzdak/snac_24khz",
                                  token="[token]")
snac_model = snac_model.to("cuda")
```

```python
import torch
import gc
from IPython.display import display, Audio

def generate_audio_from_prompt(
    prompt: str,
    chosen_voice: str,
    model,
    tokenizer,
    snac_model,
    display_result: bool = True
) -> torch.Tensor:
    """
    Generates audio from a text prompt, with explicit memory cleanup steps.

    Args:
        prompt (str): The text prompt to generate audio for.
        chosen_voice (str): The voice to use for the prompt (e.g., "christopher").
        model: The pre-loaded main language model.
        tokenizer: The pre-loaded tokenizer for the language model.
        snac_model: The pre-loaded SNAC audio model.
        display_result (bool): If True, prints the prompt and displays an audio player.

    Returns:
        torch.Tensor: The generated audio waveform as a PyTorch tensor on the CPU.
    """

    # --- Helper function for audio decoding ---
    def redistribute_codes(code_list, device):
        """Restructures flat code list and places tensors on the correct device."""
        layer_1, layer_2, layer_3 = [], [], []
        for i in range(len(code_list) // 7):
            base_idx = 7 * i
            layer_1.append(code_list[base_idx])
            layer_2.append(code_list[base_idx + 1] - 4096)
            layer_3.append(code_list[base_idx + 2] - (2 * 4096))
            layer_3.append(code_list[base_idx + 3] - (3 * 4096))
            layer_2.append(code_list[base_idx + 4] - (4 * 4096))
            layer_3.append(code_list[base_idx + 5] - (5 * 4096))
            layer_3.append(code_list[base_idx + 6] - (6 * 4096))

        codes = [
            torch.tensor(layer_1, device=device, dtype=torch.long).unsqueeze(0),
            torch.tensor(layer_2, device=device, dtype=torch.long).unsqueeze(0),
            torch.tensor(layer_3, device=device, dtype=torch.long).unsqueeze(0)
        ]
        audio_hat = snac_model.decode(codes)
        return audio_hat

    device = model.device

    with torch.inference_mode():
        formatted_prompt = f"{chosen_voice}: {prompt}" if chosen_voice else prompt
        input_ids = tokenizer(formatted_prompt, return_tensors="pt").input_ids

        start_token = torch.tensor([[128259]], dtype=torch.int64)
        end_tokens = torch.tensor([[128009, 128260]], dtype=torch.int64)
        modified_input_ids = torch.cat([start_token, input_ids, end_tokens], dim=1)

        generated_ids = model.generate(
            input_ids=modified_input_ids.to(device),
            max_new_tokens=2048,
            do_sample=True,
            temperature=0.6,
            top_p=0.95,
            repetition_penalty=1.1,
            num_return_sequences=1,
            eos_token_id=128258,
            use_cache=True
        )

        token_to_find = 128257
        token_to_remove = 128258

        token_indices = (generated_ids == token_to_find).nonzero(as_tuple=True)
        if len(token_indices[1]) > 0:
            last_occurrence_idx = token_indices[1][-1].item()
            cropped_tensor = generated_ids[:, last_occurrence_idx + 1:]
        else:
            cropped_tensor = generated_ids

        processed_tensor = cropped_tensor[cropped_tensor != token_to_remove]

        row_length = processed_tensor.size(0)
        new_length = (row_length // 7) * 7
        trimmed_tensor = processed_tensor[:new_length]

        code_list = [t.item() - 128266 for t in trimmed_tensor.cpu()]

        samples_gpu = redistribute_codes(code_list, device=device)
        samples_cpu = samples_gpu.squeeze().cpu()

    del generated_ids
    del cropped_tensor
    del processed_tensor
    del trimmed_tensor
    del code_list
    del samples_gpu
    if 'modified_input_ids' in locals(): del modified_input_ids

    gc.collect()
    torch.cuda.empty_cache()

    if display_result:
        print(f"Prompt: {prompt}")
        display(Audio(samples_cpu.numpy(), rate=24000))

    return samples_cpu
```

```python
my_prompt = "Hello I can speak in English as christopher, one of the voices I can speak."
my_voice = "christopher"

# Call the function to generate and display the audio
generated_audio_tensor = generate_audio_from_prompt(
    prompt=my_prompt,
    chosen_voice=my_voice,
    model=model,
    tokenizer=tokenizer,
    snac_model=snac_model
)
```

The Notebooks Folder For more detailed examples

## Access & Usage

The models are openly accessible and available for research and development purposes:

**🔗 [HuggingFace Model Hub](https://huggingface.co/uganda-tts-models)**

All models are provided under an open-source license, encouraging collaboration and further development in African language technologies.

---

## Limitations

While these models represent significant progress in Ugandan language TTS, there are some current limitations:

- **Non-English Language Quality**: The non-English models may occasionally produce lower quality outputs compared to the English model. This is primarily due to the SNAC audio codec not being pre-trained on these languages, which affects the initial audio token generation quality.

- **Speaker Consistency**: Non-English voices may sometimes generate speech that does not perfectly match the specified speaker characteristics due to limited training data for certain voice-language combinations.

- **Language Coverage**: Current models focus on five major Ugandan languages, with plans to expand to additional languages based on data availability and community needs.

**Note**: We are actively working on an improved version that addresses these limitations, including training SNAC on a more diverse set of languages and expanding the training datasets for better speaker fidelity.

---

## Future Work

### Completed ✅
- [x] Train the models for each of the languages
- [x] Open source the models

### In Progress 🔄
- [ ] Develop a Python package to act as an API for the models
- [ ] Improve SNAC training for better non-English language support
- [ ] Expand training datasets for enhanced speaker consistency

---

## Citation

If you use these models in your research or applications, please cite:

```bibtex
@misc{uganda_tts_2025,
    author = {Kisejjere Rashid and Magala Reuben},
    title = {Uganda Text-to-Speech (TTS) Models},
    year = {2025},
    howpublished = {\url{https://huggingface.co/USOAL}},
    note = {Fine-tuned versions of Orpheus 3B for Ugandan languages}
}
