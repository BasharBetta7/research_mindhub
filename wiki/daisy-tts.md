# Daisy-TTS

**Summary**: Daisy-TTS is an emotional TTS model that simulates primary emotions, secondary emotions, intensity levels, and emotion polarity by decomposing emotionally separable prosody embeddings. It is relevant to emotion-control concepts, but it is not direct evidence for emotional voice conversion or speaker drift.

**Sources**:
- Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf

**Last updated**: 2026-05-06

---

## Problem

Daisy-TTS targets emotional text-to-speech rather than emotional voice conversion (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). The paper argues that emotional speech systems should represent more than fixed primary emotion labels, because speech can express intensity variation, mixtures of emotions, and emotion polarity (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

## Method

Daisy-TTS uses Grad-TTS as the TTS backbone and conditions it on a prosody embedding extracted from mel-spectrogram, pitch contour, and energy contour features (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). The prosody encoder is trained with an emotion discriminator to learn emotionally separable prosody embeddings (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

The core mechanism is [[prosody-embedding-decomposition]], where the learned prosody embedding is decomposed with PCA-like prototype directions and manipulated to simulate different emotion structures (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). The paper uses this representation to synthesize primary emotions, secondary emotions, intensity levels, and polar emotions (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

## Relation To Emotion Control

Daisy-TTS controls intensity by scaling the decomposed emotion basis: values below 1.0 lower intensity and values above 1.0 intensify the emotion (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). This makes Daisy-TTS relevant to [[emotion-intensity-control]], although it is a TTS system rather than an EVC system.

Daisy-TTS models secondary emotions as mixtures of primary emotions, such as bittersweetness from joy and sadness, delight from joy and surprise, pride from joy and anger, disappointment from sadness and surprise, envy from anger and sadness, and outrage from anger and surprise (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). This connects it to [[mixed-emotion-synthesis]].

## Evaluation

The paper evaluates speech naturalness with MOS and emotion perceivability with a human emotion perception test (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). Daisy-TTS reports higher overall naturalness and emotion perceivability than the baseline from Zhou et al. 2022b, except for some emotion-specific cases such as sadness or disappointment (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

## Caution

Daisy-TTS is useful for thinking about broader emotion control, but it should not be used as direct evidence for the [[speaker-emotion-tradeoff]] in EVC because it does not perform voice conversion or measure speaker drift under emotion conversion (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

## Related pages

- [[prosody-embedding-decomposition]]
- [[mixed-emotion-synthesis]]
- [[emotion-intensity-control]]
- [[spectrum-prosody-conversion]]
- [[synthetic-emotional-speech-data]]
- [[speaker-emotion-tradeoff]]

