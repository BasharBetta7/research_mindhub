# EINet

**Summary**: EINet is an emotional intensity-aware EVC model that uses VAD-based intensity pseudo-labels to improve realistic emotion conversion. It is direct evidence for controllable emotional intensity in EVC.

**Sources**:
- Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf

**Last updated**: 2026-05-06

---

## Problem

EINet targets realistic emotional voice conversion, where converted speech should preserve linguistic content and speaker identity while expressing more diverse and natural target emotions (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

The paper argues that many EVC systems improve speech quality but still lack emotional diversity, making controllable emotional intensity important for realistic synthesis (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

## Method

EINet is built on a conditional variational autoencoder with adversarial training and includes a posterior network, intensity mapper, prior network, and decoder (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

The key mechanism is [[vad-based-emotion-intensity]], where an emotion evaluator predicts utterance-level valence, arousal, and dominance values and an intensity mapper constructs intensity pseudo-labels from those emotional states (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

The intensity mapper is built with reversible normalizing flow, so during inference a target emotion category and scalar intensity value can be mapped back into VAD values for controlled conversion (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

EINet includes an identity maintainer that constrains F0 and voicing behavior to reduce speaker identity loss under stronger acoustic manipulation (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

The emotion renderer expands VAD values into frame-level emotional acoustic features and combines them with linguistic features (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf). The duration predictor conditions on emotional and linguistic features to model rhythm changes under different emotional intensities (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

## Data and evaluation

The experiments use the Mandarin corpus in ESD and perform conversions from neutral to angry, happy, sad, and surprise (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

For each conversion pair, the paper uses 300 training samples, 30 validation samples, and 20 test samples (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

Objective evaluation uses MCD, log-F0 RMSE, average duration difference, and classification accuracy from an external pretrained SER model (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf). Subjective evaluation uses MOS tests with 25 participants to assess naturalness and emotion similarity (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

## Results

EINet reports MCD 4.06, log-F0 RMSE 38.28, DDUR 0.21, SER classification accuracy 99.48%, naturalness 4.38 +- 0.05, and similarity 75.18% (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

Compared with VITS-EVC, EINet reduces log-F0 RMSE from 41.42 to 38.28 and DDUR from 0.29 to 0.21 while improving naturalness from 4.14 +- 0.08 to 4.38 +- 0.05 and similarity from 70.07% to 75.18% (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

Ablation results show that removing the identity maintainer, emotion renderer, or duration predictor degrades naturalness and objective metrics (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

The controllability visualizations show broader pitch fluctuation, higher peak energy, stronger acoustic variation, and more short pauses as emotional intensity increases (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

## Caution

EINet is direct EVC evidence for intensity control, but its speaker-identity evaluation is still indirect because the main reported table does not include a standard speaker-similarity metric such as SECS, sMOS, or EER (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

The identity maintainer is explicitly motivated by identity loss under controllable EVC, so EINet is relevant to [[speaker-emotion-tradeoff]], but it does not provide a full speaker-emotion Pareto frontier (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

## Related pages

- [[vad-based-emotion-intensity]]
- [[emotion-intensity-control]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[duration-flexible-evc]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emovox]]
