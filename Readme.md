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

## Audio Examples

### English

**Christopher**  
*Prompt*: "Hello I can speak in English as christopher, one of the voices I can speak."  
[Listen to Christopher's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/christopher.wav)

**Barbara**  
*Prompt*: "Or as barbra, this is one of my female voices. Pretty cool right?."  
[Listen to Barbara's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/barbara.wav)

**Mary**  
*Prompt*: "I can also speak as Mary as well."  
[Listen to Mary's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/mary.wav)

**James**  
*Prompt*: "Or I can speak as james as you can see."  
[Listen to James' message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/james.wav)

**Jessica**  
*Prompt*: "This is my other voice called jessica, I have more voices of jennifer, suzan, linda, patricia and elizabeth. But I will be sharing these voices once I am fully done from baking."  
[Listen to Jessica's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/English/jessica.wav)

### Luganda

**Christopher**  
*Prompt*: "Nsobolla okwo'geranga Christopher nga wowulila kati."  
[Listen to Christopher's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/christopher.wav)

**Charles**  
*Prompt*: "Oba neenjogela nga charles wenti."  
[Listen to Charles' message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/charles.wav)

**Sandra**  
*Prompt*: "Nina neddoboozi lya Sandra bweliti."  
[Listen to Sandra's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/sandra.wav)

**Michelle**  
*Prompt*: "Nsobolla ogwogella bwenti mulino eddoboozi."  
[Listen to Michelle's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/michelle.wav)

**Daniel**  
*Prompt*: "Oba nemulino elye'kisajja nga woowulira."  
[Listen to Daniel's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/daniel.wav)

**Margaret**  
*Prompt*: "Charlissi yimilila awo."  
[Listen to Margaret's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/margaret.wav)

**Mark**  
*Prompt*: "Ninna amaloboozi amalala naye nja kugalaga nga mazze oku tureyininga."  
[Listen to Mark's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Luganda/mark.wav)

### Runyonkole

**Christopher**  
*Prompt*: "Nimbasa kugamba nka Christopher omwiraka eri."  
[Listen to Christopher's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/christopher.wav)

**Michelle**  
*Prompt*: "Nimbasa kugamba nka Michelle omwiraka eri."  
[Listen to Michelle's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/michelle.wav)

**James**  
*Prompt*: "Uganda eteire amaani aha buhingi n'oburiisa."  
[Listen to James' message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/james.wav)

**Patricia**  
*Prompt*: "Bimwe ebirikugambwa aha reediyo nibihwera abantu kumanya obutare burungi bw'amasharuura gaabo."  
[Listen to Patricia's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/patricia.wav)

**Charles**  
*Prompt*: "Okukyerererwa kufuuhirira nikyo kirikutokooza ebyokurya ebitwine ebiro ebi."  
[Listen to Charles' message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/charles.wav)

**Elizabeth**  
*Prompt*: "Omu disiturikiti ya Kayunga emisiri erikukira obwngi ekashangwa erimu ebicoori ebiine oburwaire."  
[Listen to Elizabeth's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Runyankole/elizabeth.wav)

### Tesso

**Christopher**  
*Prompt*: "Epedorete akoriok aimedaun ejok kanejaas aicoreta nu itikitikere adeka."  
[Listen to Christopher's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/christopher.wav)

**Jessica**  
*Prompt*: "Akoru ikorion luegelegela nes ingarakini itunganan."  
[Listen to Jessica's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/jessica.wav)

**James**  
*Prompt*: "Iraasit yen emunaara aticepak ikur enyamitos."  
[Listen to James' message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/james.wav)

**Daniel**  
*Prompt*: "Aipagisanar nes ewai ecie lo ibwaikinet iboro toma aswam."  
[Listen to Daniel's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/daniel.wav)

**Barbara**  
*Prompt*: "Isisianakinete isomeroi kwana asiomak eipone lo isubusaere."  
[Listen to Barbara's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Teso/barbara.wav)

### Acholi

**Mark**  
*Prompt*: "Uganda tye ka keme ki lok me pur."  
[Listen to Mark's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Acholi/mark.wav)

**Barbara**  
*Prompt*: "Lupur twero nongo kony ma dit ka gunongo ngec me gengo onyo cango two ma balo jami ma i poto."  
[Listen to Barbara's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Acholi/barbara.wav)

**James**  
*Prompt*: "Ler ma pe gidodo ma woto ka yenyo cam i dye poto obalo cam weng ma tye i poto."  
[Listen to James' message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Acholi/james.wav)

**Michelle**  
*Prompt*: "Gum madwong me timo biacara tye i te yub ma pe jenge i kom gamente."  
[Listen to Michelle's message](https://github.com/Uganda-lang/Ganda-TTS/raw/refs/heads/main/Example/Acholi/mitchelle.wav)

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
