# Parallel Emotional Speech Data

**Summary**: Parallel emotional speech data contains matched utterances spoken with different emotions, usually by the same speaker. It is especially important for sequence-to-sequence EVC, but scarcity of large high-quality parallel data is a recurring bottleneck.

**Sources**:
- Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf
- Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf
- Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf

**Last updated**: 2026-05-06

---

## Definition

Parallel emotional speech data contains the same linguistic content spoken under different emotional conditions, often by the same speaker (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). Seq2Seq EVC benefits from this setup because the model can learn emotion conversion while also learning alignment and duration changes (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

## Why It Matters

The survey identifies dataset availability as the main challenge for [[sequence-to-sequence-emotional-voice-conversion]], because Seq2Seq training usually needs large parallel emotional datasets (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). The paper states that existing public datasets are small or have quality limitations, which makes comparison and scaling difficult (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

[[deepest]] released ESD, a multilingual and multi-speaker emotional speech dataset intended for voice conversion and related speech synthesis tasks (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). Yang et al. describe ESD as clean and parallel, but note that it has only 350 utterances per speaker (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

[[zhou-2022-evc-theory-esd]] is the canonical ESD reference: it reports 350 parallel utterances per speaker per emotion from 10 English and 10 Chinese speakers across neutral, happy, angry, sad, and surprise (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). It partitions each speaker-emotion set into 20 evaluation, 30 test, and 300 training utterances (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Research Responses

Two-stage training is one response to limited parallel emotional data: a model can first learn style or speech generation from a larger TTS dataset and then fine-tune on a smaller emotional dataset (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). This idea connects to [[style-pretraining-for-evc]] and [[emovox]].

Non-parallel approaches address the same bottleneck from another direction. [[emoconv-diff]] explicitly targets non-parallel in-the-wild emotion conversion, while [[durflex-evc]] avoids text and speech-text alignment by using discrete units and duration modelling (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

[[sgevc]] is a semi-supervised response to the label side of this bottleneck: it still uses ESD, but it reports emotion control with as little as 1% labeled emotional data by combining supervised and unsupervised generative objectives (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Related pages

- [[sequence-to-sequence-emotional-voice-conversion]]
- [[deepest]]
- [[style-pretraining-for-evc]]
- [[emovox]]
- [[duration-flexible-evc]]
- [[non-parallel-voice-conversion]]
- [[emoconv-diff]]
- [[durflex-evc]]
- [[zhou-2022-evc-theory-esd]]
- [[esd-dataset]]
- [[sgevc]]
- [[semi-supervised-evc]]
