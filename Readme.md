# Uganda Text-to-Speech (TTS) Models

A new suite of Text-to-Speech (TTS) models for Ugandan languages: **English, Luganda, Runyonkole, Tesso, and Acholi**. These models support multiple speakers per language and are openly accessible for research and development.

---

## Table of Contents

- [Overview](#overview)
- [Supported Languages & Voices](#supported-languages--voices)
    - [English](#english)
    - [Luganda](#luganda)
    - [Runyonkole](#runyonkole)
    - [Tesso](#tesso)
    - [Acholi](#acholi)
- [Access](#access)
- [Limitations](#limitations)
- [Citation](#citation)
- [TODO](#todo)

---

## Overview

This project launches TTS models for five Ugandan languages, each with multiple speaker voices. The models are available for open access and experimentation.

---

## Supported Languages & Voices

### English

Supported voices:
- Barbara
- Mary
- Jennifer
- Jessica
- Susan
- James
- Linda
- Patricia
- Elizabeth
- Christopher

#### Examples

- **Christopher**  
    [Audio Sample](path/to/english_christopher_sample.mp3)
- **Barbara**  
    [Audio Sample](path/to/english_barbara_sample.mp3)
- **Mary**  
    [Audio Sample](path/to/english_mary_sample.mp3)
- *(...other voices)*

---

### Luganda

Supported voices:
- Charles
- Sandra
- Christopher
- Mark
- Barbara
- Michelle
- Karen
- James
- Margaret
- Daniel

#### Examples

- **Charles**  
    [Audio Sample](path/to/luganda_charles_sample.mp3)
- **Sandra**  
    [Audio Sample](path/to/luganda_sandra_sample.mp3)
- **Christopher**  
    [Audio Sample](path/to/luganda_christopher_sample.mp3)
- *(...other voices)*

---

### Runyonkole

Supported voices:
- Michelle
- James
- Patricia
- Mark
- Elizabeth
- Charles
- Daniel
- Barbara
- Christopher
- Linda

#### Examples

- **Michelle**  
    [Audio Sample](path/to/runyonkole_michelle_sample.mp3)
- **James**  
    [Audio Sample](path/to/runyonkole_james_sample.mp3)
- **Patricia**  
    [Audio Sample](path/to/runyonkole_patricia_sample.mp3)
- *(...other voices)*

---

### Tesso

Supported voices:
- Mitchelle
- Barbara
- Jessica
- Christopher
- James
- Daniel
- Charles
- Mark

#### Examples

- **Mitchelle**  
    [Audio Sample](path/to/tesso_mitchelle_sample.mp3)
- **Barbara**  
    [Audio Sample](path/to/tesso_barbara_sample.mp3)
- **Jessica**  
    [Audio Sample](path/to/tesso_jessica_sample.mp3)
- *(...other voices)*

---

### Acholi

Supported voices:
- James
- Barbara
- Mitchelle
- Mark
- Christopher

#### Examples

- **James**  
    [Audio Sample](path/to/acholi_james_sample.mp3)
- **Barbara**  
    [Audio Sample](path/to/acholi_barbara_sample.mp3)
- **Mitchelle**  
    [Audio Sample](path/to/acholi_mitchelle_sample.mp3)
- *(...other voices)*

---

## Access

The models are openly accessible via HuggingFace:  
[https://huggingface.co/uganda-tts-models](https://huggingface.co/uganda-tts-models) *(dummy link)*

---

## Limitations

- Non-English voices may sometimes generate speech that does not match the specified speaker due to limited training data.
- Ongoing work is being done to improve speaker fidelity and language coverage.

---

## Citation

If you use these models, please cite:

```
@misc{uganda_tts_2024,
    author = {Kisejjere Rashid and Magal Reuben},
    title = {Uganda Text-to-Speech (TTS) Models},
    year = {2024},
    howpublished = {\url{https://huggingface.co/uganda-tts-models}}
}
```

---

## TODO

### Completed
- [x] Train the models for each of the languages
- [x] Open source the models

### Not Yet Completed
- [ ] Generate a Python package to act as an API for the models
- [ ] Write a white paper detailing the process
