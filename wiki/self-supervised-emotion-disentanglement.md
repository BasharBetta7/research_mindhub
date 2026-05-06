# Self-Supervised Emotion Disentanglement

**Summary**: Self-supervised emotion disentanglement aims to learn emotion representations while reducing speaker leakage without relying only on explicit adversarial speaker labels. DiEmo-TTS uses a DINO-style teacher-student setup for this problem.

**Sources**:
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf

**Last updated**: 2026-05-06

---

## Definition

Self-supervised emotion disentanglement learns emotion embeddings that preserve emotional information while suppressing irrelevant factors such as speaker identity (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). In [[diemo-tts]], this is framed as necessary for [[cross-speaker-emotion-transfer]] because speaker leakage can compromise the target timbre (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## DiEmo-TTS Method

DiEmo-TTS uses a DINO-style teacher-student distillation method with cluster-driven sampling, formant-based information perturbation, and cosine-similarity loss (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). The paper argues that this avoids some limitations of GRL and vector-quantization approaches, which can lose emotional information or require difficult optimization (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## Relation To The Tradeoff

This concept is adjacent to EVC because it directly addresses the speaker-emotion separation problem, but the evidence comes from TTS rather than voice conversion (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). It is therefore relevant to [[speaker-emotion-tradeoff]] as a modelling idea, not as direct EVC speaker-drift measurement.

## Related pages

- [[diemo-tts]]
- [[cross-speaker-emotion-transfer]]
- [[speaker-disentanglement]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]

