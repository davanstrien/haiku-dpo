<h1 align="center">🌸 Synthetic Haiku DPO 🌸</h1>
<p align="center"><em> Using open source LLMs to build synthetic datasets for direct preference optimization </em></p>
<p align="center">
    <img src="https://cdn-uploads.huggingface.co/production/uploads/60107b385ac3e86b3ea4fc34/nmz7lvu64BytxDvPMm1C5.png" alt="Banner for a dataset card featuring a fusion of digital and traditional Japanese elements. The design includes stylized digital prompts and haiku within text bubbles and on digital screens, set against a backdrop of delicate cherry blossoms and a serene Japanese landscape. The color scheme is dominated by soft pastel pink tones, creating a harmonious blend of modern technology and classical poetry aesthetics." width="500">
</p>

<p align="center"><em>Lines in code retreat,<br>Synthetic haiku compete,<br>Nature's rhythm, neat.<br></em></p>

## 📖 About

[<img src="https://raw.githubusercontent.com/argilla-io/distilabel/main/docs/assets/distilabel-badge-light.png" alt="Built with Distilabel" width="200" height="32"/>](https://github.com/argilla-io/distilabel)

> Haiku (俳句) is a type of short form poetry that originated in Japan. Traditional Japanese haiku consist of three phrases composed of 17 phonetic units (called on in Japanese, which are similar to syllables) in a 5, 7, 5 pattern  - [https://en.wikipedia.org/wiki/Haiku](https://en.wikipedia.org/wiki/Haiku)


A current request for a haiku looks like when using the [TinyLlama/TinyLlama-1.1B-Chat-v1.0](https://huggingface.co/TinyLlama/TinyLlama-1.1B-Chat-v1.0) model looks like this:

```bash
>>> Write a haiku about moss.
Mosses soft, green and shining,
Gracefully drifting in the breeze,
A symphony of light and sound.
```

This has some of the properties of a traditional haiku (as expressed in the English language), it has three lines, and the themes of nature and the seasons are present. However, the syllable count is off. 

What happens if we do a little prompt engineering and ask the model to write a haiku with a 5, 7, 5 syllable pattern? 

```bash
>>> Write a haiku about moss. Follow the traditional 5-7-5 syllable pattern.
Mosses, tiny green eyes, inchworm life,
Growing tall, they're hard to see,
Syllables flow, as the world moves by: haiku of life.
```

Prompt engineering didn't help use here. What if we use a slightly larger model? The [teknium/OpenHermes-2.5-Mistral-7B](https://huggingface.co/teknium/OpenHermes-2.5-Mistral-7B) model is a 7B parameter model, which I've found to perform very well for many tasks. 

```bash
>>> Write a haiku about moss. Follow the traditional 5-7-5 syllable pattern.
Moss, soft emerald hue,
Creeps on stone, whispers secrets -
Nature's silent truth.
```


This repository contains the code used to generate the [Synthetic Haiku DPO](https://huggingface.co/datasets/davanstrien/haiku_dpo) dataset, a dataset of synthetic haiku generated using [Distilabel](https://github.com/argilla-io/distilabel). 

The goal of this repo is to help the author explore the process of using synthetic data to train a model for direct preference optimization (DPO). 

