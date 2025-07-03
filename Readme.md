# Uganda Text-to-Speech (TTS) Models

**🔗 [Access Models on HuggingFace](https://huggingface.co/Uganda-lang)**

A comprehensive suite of Text-to-Speech (TTS) models for Ugandan languages, supporting **English, Luganda, Runyonkole, Tesso, and Acholi** with multiple speaker voices for each language.

---

## Table of Contents

- [Introduction](#introduction)
- [Model Architecture](#model-architecture)
- [Supported Languages & Voices](#supported-languages--voices)
- [Audio Examples](#audio-examples)
- [Access & Usage](#access--usage)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [Citation](#citation)

---

## Introduction

This project introduces a groundbreaking collection of Text-to-Speech models specifically designed for Ugandan languages. These models represent a significant advancement in African language technology, addressing the critical gap in speech synthesis capabilities for Uganda's diverse linguistic landscape.

The Uganda TTS model family consists of fine-tuned versions of the **Orpheus 3B model**, each specialized for different Ugandan languages while maintaining high-quality speech synthesis capabilities. Each language model supports multiple distinct speaker voices, enabling versatile applications in education, accessibility, content creation, and digital preservation of Ugandan languages.

These models are designed to serve researchers, developers, educators, and content creators who need high-quality speech synthesis in Ugandan languages, contributing to the broader goal of digital language preservation and accessibility in Africa.

## Model Architecture

The Uganda TTS models utilize a sophisticated two-stage architecture:

1. **Audio Token Generation**: The models generate audio tokens based on the SNAC (Structured Neural Audio Codec) framework
2. **Fine-tuned Processing**: These audio tokens are then processed through specialized fine-tuned versions of the Orpheus 3B model, each optimized for specific Ugandan languages

This architecture enables efficient and high-quality speech synthesis while maintaining computational efficiency suitable for various deployment scenarios.

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

## Audio Examples

### English

**Christopher**  
*Prompt*: "Hello I can speak in English as christopher, one of the voices I can speak."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/christopher.wav"></audio>

**Barbara**  
*Prompt*: "Or as barbra, this is one of my female voices. Pretty cool right?."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/barbara.wav"></audio>

**Mary**  
*Prompt*: "I can also speak as Mary as well."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/mary.wav"></audio>

**James**  
*Prompt*: "Or I can speak as james as you can see."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/james.wav"></audio>

**Jessica**  
*Prompt*: "This is my other voice called jessica, I have more voices of jennifer, suzan, linda, patricia and elizabeth. But I will be sharing these voices once I am fully done from baking."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/jessica.wav"></audio>

### Luganda

**Christopher**  
*Prompt*: "Nsobolla okwo'geranga Christopher nga wowulila kati."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/christopher.wav"></audio>

**Charles**  
*Prompt*: "Oba neenjogela nga charles wenti."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/charles.wav"></audio>

**Sandra**  
*Prompt*: "Nina neddoboozi lya Sandra bweliti."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/sandra.wav"></audio>

**Michelle**  
*Prompt*: "Nsobolla ogwogella bwenti mulino eddoboozi."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/michelle.wav"></audio>

**Daniel**  
*Prompt*: "Oba nemulino elye'kisajja nga woowulira."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/daniel.wav"></audio>

**Margaret**  
*Prompt*: "Charlissi yimilila awo."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/margaret.wav"></audio>

**Mark**  
*Prompt*: "Ninna amaloboozi amalala naye nja kugalaga nga mazze oku tureyininga."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/mark.wav"></audio>

### Runyonkole

**Christopher**  
*Prompt*: "Nimbasa kugamba nka Christopher omwiraka eri."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/christopher.wav"></audio>

**Michelle**  
*Prompt*: "Nimbasa kugamba nka Michelle omwiraka eri."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/michelle.wav"></audio>

**James**  
*Prompt*: "Uganda eteire amaani aha buhingi n'oburiisa."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/james.wav"></audio>

**Patricia**  
*Prompt*: "Bimwe ebirikugambwa aha reediyo nibihwera abantu kumanya obutare burungi bw'amasharuura gaabo."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/patricia.wav"></audio>

**Charles**  
*Prompt*: "Okukyerererwa kufuuhirira nikyo kirikutokooza ebyokurya ebitwine ebiro ebi."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/charles.wav"></audio>

**Elizabeth**  
*Prompt*: "Omu disiturikiti ya Kayunga emisiri erikukira obwngi ekashangwa erimu ebicoori ebiine oburwaire."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/elizabeth.wav"></audio>

### Tesso

**Christopher**  
*Prompt*: "Epedorete akoriok aimedaun ejok kanejaas aicoreta nu itikitikere adeka."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/christopher.wav"></audio>

**Jessica**  
*Prompt*: "Akoru ikorion luegelegela nes ingarakini itunganan."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/jessica.wav"></audio>

**James**  
*Prompt*: "Iraasit yen emunaara aticepak ikur enyamitos."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/james.wav"></audio>

**Daniel**  
*Prompt*: "Aipagisanar nes ewai ecie lo ibwaikinet iboro toma aswam."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/daniel.wav"></audio>

**Barbara**  
*Prompt*: "Isisianakinete isomeroi kwana asiomak eipone lo isubusaere."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/barbara.wav"></audio>

### Acholi

**Mark**  
*Prompt*: "Uganda tye ka keme ki lok me pur."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Acholi/mark.wav"></audio>

**Barbara**  
*Prompt*: "Lupur twero nongo kony ma dit ka gunongo ngec me gengo onyo cango two ma balo jami ma i poto."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Acholi/barbara.wav"></audio>

**James**  
*Prompt*: "Ler ma pe gidodo ma woto ka yenyo cam i dye poto obalo cam weng ma tye i poto."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Acholi/james.wav"></audio>

**Michelle**  
*Prompt*: "Gum madwong me timo biacara tye i te yub ma pe jenge i kom gamente."
<audio controls src="https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Acholi/mitchelle.wav"></audio>

---

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
- [ ] Write a comprehensive white paper detailing the training process and methodology
- [ ] Improve SNAC training for better non-English language support
- [ ] Expand training datasets for enhanced speaker consistency

---

## Citation

If you use these models in your research or applications, please cite:

```bibtex
@misc{uganda_tts_2024,
    author = {Kisejjere Rashid and Magala Reuben},
    title = {Uganda Text-to-Speech (TTS) Models},
    year = {2024},
    howpublished = {\url{https://huggingface.co/Uganda-lang}},
    note = {Fine-tuned versions of Orpheus 3B for Ugandan languages}
}
```

---

**Contributing**: We welcome contributions, feedback, and collaboration from the community. Please feel free to open issues or submit pull requests to help improve these models.

**Contact**: For questions, collaborations, or support, please reach out through the HuggingFace model repository or create an issue in our GitHub repository.