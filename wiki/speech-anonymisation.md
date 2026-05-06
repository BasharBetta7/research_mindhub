# Speech Anonymisation

**Summary**: Speech anonymisation modifies speech to prevent tracing it back to the original speaker. Emo-StarGAN frames voice conversion as anonymisation that should preserve linguistic content and emotion.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Speech anonymisation prevents misuse of spoken data by removing personal identifiers while preserving at least linguistic content (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). The Emo-StarGAN paper motivates anonymisation by risks from cloud-based speech devices and possible misuse of spoken data for impersonation or speaker verification bypass (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Relation to emotion

The paper argues that preserving emotion is important when a system response depends on the user's emotional state, such as a digital assistant responding differently when the user sounds sad (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). [[emo-stargan]] therefore treats anonymisation as a conversion task where speaker identity changes while linguistic and emotional content should remain (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[emo-stargan]]
- [[emotion-preserving-voice-conversion]]
- [[voice-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
