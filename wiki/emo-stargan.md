# Emo-StarGAN

**Summary**: Emo-StarGAN is a semi-supervised any-to-many non-parallel voice conversion framework that extends StarGANv2-VC to preserve source emotion during speaker anonymisation. It adds emotion classifier, emotion embedding, and acoustic feature losses.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Core idea

Emo-StarGAN adapts [[starganv2-vc]] for [[speech-anonymisation]] where speaker identity is changed while linguistic and emotional content should be preserved (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). The authors argue that vanilla StarGANv2-VC produces strong anonymisation but fails to preserve emotion, especially for diverse emotions and acoustic conditions with highly varying pitch (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

The framework is any-to-many, semi-supervised, and non-parallel, using partially emotion-labelled data to improve [[emotion-preserving-voice-conversion]] (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). It keeps StarGANv2-VC losses for speaker conversion and adds emotion-aware losses to preserve source emotion after conversion (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Emotion supervision

Emo-StarGAN uses direct supervision through [[emotion-classifier-loss]] when source emotion labels are available (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). It also uses indirect supervision through [[emotion-embedding-loss]] and [[emotion-aware-acoustic-feature-loss]], which compare source and converted samples using emotion-related representations (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

The acoustic feature loss considers spectral centroid, spectral kurtosis, loudness, and F0 change; spectral kurtosis is selected as the best feature in their ablation (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). The emotion embedding loss uses a two-stage setup where a StarGANv2-VC-style emotion conversion model first learns emotion embeddings and is then fine-tuned for automatic embedding extraction (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Results

Across all conversions, Emo-StarGAN improves Accorig from 20.2% to 72.4%, Accsvm from 39.4% to 87.1%, embedding MAE from 48.9 to 40.8, and PCC from 78.9 to 84.3 while keeping EER almost unchanged at 49.63 versus 49.64 (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). Subjective raters preferred Emo-StarGAN for emotion preservation 840 times versus 327 for the baseline, and rated its MOS 4.20 versus 4.09 for the baseline (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

The ablation reports that [[emotion-embedding-loss]] contributes the most to emotion preservation among the individual proposed losses, while each individual proposed technique improves emotion preservation over the baseline (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

These aggregate results are the current wiki's strongest evidence about the [[speaker-emotion-tradeoff]], because emotion preservation improves substantially while anonymisation EER remains almost unchanged (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Limitations

The paper reports weaker performance for surprise than for other emotions: surprise Accorig is 16.0% in ESD to ESD and 0.0% in RAVDESS to ESD (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). The authors identify complex emotions as a future-work direction and propose emotion-specific losses and embeddings learned from multi-label or arousal-valence datasets (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[starganv2-vc]]
- [[speech-anonymisation]]
- [[emotion-preserving-voice-conversion]]
- [[emotion-classifier-loss]]
- [[emotion-embedding-loss]]
- [[emotion-aware-acoustic-feature-loss]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emotional-speech-conversion]]
- [[speaker-emotion-tradeoff]]
