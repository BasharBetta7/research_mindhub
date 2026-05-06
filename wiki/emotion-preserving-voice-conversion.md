# Emotion-Preserving Voice Conversion

**Summary**: Emotion-preserving voice conversion changes speaker identity while preserving the source utterance's emotional content. Emo-StarGAN targets this setting by adding direct and indirect emotion supervision to StarGANv2-VC.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Emotion-preserving voice conversion aims to modify speaker timbre while preserving source linguistic and emotional content (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). In [[emo-stargan]], the task is motivated by [[speech-anonymisation]] rather than by generating a target emotion different from the source emotion (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

This setup naturally raises the [[speaker-emotion-tradeoff]], because speaker identity should be changed or hidden while emotional content should remain stable (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Difference from emotional conversion

Emotion preservation is not the same as converting neutral speech into a target emotion (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). [[emotional-speech-conversion]] can refer broadly to target-emotion generation, while Emo-StarGAN specifically tries to keep the original emotion unchanged during speaker conversion (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

[[emovox]] is closer to target-emotion generation because it transfers a reference emotion to source speech and controls the target emotion intensity, while preserving linguistic content and speaker identity (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). This makes Emovox complementary to Emo-StarGAN rather than a direct replacement for emotion-preserving anonymisation (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf; source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[emo-stargan]]
- [[emotional-speech-conversion]]
- [[speech-anonymisation]]
- [[emotion-classifier-loss]]
- [[emotion-embedding-loss]]
- [[emotion-aware-acoustic-feature-loss]]
- [[emovox]]
- [[emotion-intensity-control]]
- [[speaker-emotion-tradeoff]]
