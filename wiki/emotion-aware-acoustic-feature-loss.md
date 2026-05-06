# Emotion-Aware Acoustic Feature Loss

**Summary**: Emotion-aware acoustic feature loss compares emotion-correlated acoustic descriptors between source and converted speech. Emo-StarGAN evaluates spectral and prosodic descriptors and selects spectral kurtosis as the best acoustic feature.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Emotion-aware acoustic feature loss computes an L1 distance between acoustic descriptors of source and converted samples (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). Emo-StarGAN considers spectral centroid, spectral kurtosis, loudness, and change in F0 as differentiable descriptors correlated with emotion (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Feature categories

The paper groups spectral centroid and spectral kurtosis as spectral descriptors, and loudness and F0 change as non-spectral/prosodic descriptors (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). Spectral kurtosis is selected as AFbest because it gives the best emotion preservation in the acoustic-feature selection experiment (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Evidence

With only spectral kurtosis loss added to the baseline, Accorig improves from 20.2% to 30.1% and PCC improves from 78.9 to 80.4, but CER worsens from 3.42% to 5.52% in the ablation table (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). This suggests the acoustic feature loss helps emotion preservation but is weaker than [[emotion-embedding-loss]] in the reported ablation (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[emo-stargan]]
- [[emotion-preserving-voice-conversion]]
- [[emotion-embedding-loss]]
- [[f0-consistency-loss]]
