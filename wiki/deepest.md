# DeepEST

**Summary**: DeepEST is a one-to-many emotional style transfer framework for voice conversion that uses deep emotional features from a pretrained SER model. The paper also introduced the Emotional Speech Dataset (ESD).

**Sources**:
- Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf

**Last updated**: 2026-05-06

---

## Problem framing

DeepEST aims to transfer emotional style to an input utterance using a control condition rather than training a separate model for every emotion pair (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). It supports seen and unseen emotional style transfer by conditioning a VAW-GAN decoder on deep emotional features extracted by a pretrained SER model (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf).

## Method

The framework has three stages: train an SER emotion descriptor, train a VAW-GAN encoder-decoder conditioned on deep emotional features and F0, and perform run-time conversion using reference emotional features (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). The encoder is intended to learn an emotion-independent representation, while the decoder recomposes spectrum using the latent representation, F0, and target emotion descriptor (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf).

## ESD

The paper releases ESD, a multi-speaker and multilingual emotional speech dataset with 350 parallel utterances from 10 native English and 10 native Mandarin speakers across five emotions (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). ESD has become an important benchmark used by later EVC papers such as [[durflex-evc]] and [[pflow-vc]].

## Results

DeepEST improves MCD over VAW-GAN-EVC for seen neutral-to-happy and neutral-to-sad conversions, and remains comparable for unseen neutral-to-angry conversion (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). Subjective MOS also slightly favors DeepEST over VAW-GAN-EVC for all reported conversion settings (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf).

## Caution

The paper notes that SER performance varies by emotion, including weak performance for happy, which affects emotion similarity results (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). This makes DeepEST important evidence for [[deep-emotional-features]], but also a warning that SER-derived style descriptors can bottleneck conversion quality.

## Related pages

- [[deep-emotional-features]]
- [[seen-and-unseen-emotion-transfer]]
- [[ser-perceptual-loss]]
- [[emotional-speech-conversion]]
- [[non-parallel-voice-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
