# Cross-Speaker Emotion Transfer

**Summary**: Cross-speaker emotion transfer transfers emotion from a reference utterance to another target speaker while preserving the target speaker's timbre. DiEmo-TTS studies this in TTS and makes the emotion-speaker disentanglement problem explicit.

**Sources**:
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf

**Last updated**: 2026-05-06

---

## Definition

Cross-speaker emotion transfer synthesizes speech for a target speaker while transferring emotion from a reference utterance spoken by another speaker (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). In this setting, emotion embeddings should be speaker-independent so that source-speaker traits do not leak into the target timbre (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## Relation To Speaker Drift

The problem is adjacent to EVC speaker drift because both settings require separating emotion from speaker identity (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). DiEmo-TTS explicitly argues that disentangling speaker and emotion is difficult because some prosodic features are inherently associated with speaker identity (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

[[self-supervised-emotion-disentanglement]] is one approach to this problem, using teacher-student distillation, cluster-driven sampling, and information perturbation to reduce speaker leakage while preserving emotional information (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## Related pages

- [[diemo-tts]]
- [[speaker-emotion-tradeoff]]
- [[speaker-disentanglement]]
- [[speaker-identity-evaluation-in-evc]]
- [[self-supervised-emotion-disentanglement]]
