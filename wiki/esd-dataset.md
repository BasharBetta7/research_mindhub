# ESD Dataset

**Summary**: ESD is a bilingual parallel emotional speech dataset released for emotional voice conversion and emotional speech generation. It is one of the central benchmarks in the wiki and is especially important for evaluating speaker-independent and cross-lingual EVC.

**Sources**:
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf
- Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf
- Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf
- Didi+et+al.pdf

**Last updated**: 2026-05-07

---

## Canonical description

The canonical ESD paper reports 20 speakers: 10 native English speakers and 10 native Chinese speakers (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). Each speaker records 350 parallel utterances in five emotion categories: neutral, happy, angry, sad, and surprise (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

The paper reports more than 29 hours of studio-recorded speech with controlled recording conditions, balanced language coverage, and balanced gender settings within the English and Chinese subsets (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). Each speaker-emotion set is partitioned into 20 evaluation utterances, 30 test utterances, and 300 training utterances (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Why ESD matters

ESD was designed to address limitations in prior [[emotional-speech-databases]], especially limited lexical variability, limited speaker variability, imbalanced languages, confounding factors, and noisy recording environments (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). Because it is parallel across emotions, it supports [[parallel-emotional-speech-data]] experiments while also being used by non-parallel methods that ignore the alignment during training (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

ESD has become a common benchmark for later systems, including [[sgevc]], [[durflex-evc]], [[pflow-vc]], [[emodiff]], [[zest]], and [[textless-speech-emotion-conversion]] (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf; source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf; source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf; source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## F0 and emotion

The canonical ESD paper reports that happy and surprise generally show higher F0 mean and variance, while neutral and sad have lower F0 values (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). This makes ESD useful for studying [[f0-pitch-contour-in-voice-conversion]], but it also means speaker-gender normalization and speaker-aware analysis are important when interpreting F0 differences (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Contradiction note

The Didi et al. source states that ESD contains recordings from over 300 speakers, which conflicts with the canonical 20-speaker description from Zhou et al. 2022 (source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). Treat the 20-speaker description as the canonical ESD metadata unless a separate dataset version is explicitly documented (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

This contradiction is tracked centrally in [[source-reliability-notes]].

## Related pages

- [[zhou-2022-evc-theory-esd]]
- [[emotional-speech-databases]]
- [[parallel-emotional-speech-data]]
- [[speaker-emotion-tradeoff]]
- [[evaluation-metrics-for-voice-conversion]]
- [[f0-pitch-contour-in-voice-conversion]]
- [[deepest]]
- [[sgevc]]
- [[seq2seq-cyclegan-evc]]
- [[source-reliability-notes]]
