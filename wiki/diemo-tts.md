# DiEmo-TTS

**Summary**: DiEmo-TTS is a cross-speaker emotional TTS model that learns speaker-irrelevant emotion embeddings through self-supervised distillation. It is important adjacent evidence for the emotion-speaker tradeoff because it explicitly targets emotion transfer without target-speaker leakage.

**Sources**:
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf

**Last updated**: 2026-05-06

---

## Problem

DiEmo-TTS targets [[cross-speaker-emotion-transfer]] in text-to-speech, where emotion from a reference utterance is transferred to a different target speaker (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). The paper argues that reference-based cross-speaker emotion synthesis needs speaker-independent emotion embeddings, because residual speaker traits can affect the target timbre (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## Method

DiEmo-TTS uses self-supervised teacher-student distillation inspired by DINO to learn emotion embeddings without explicit speaker-label adversarial training (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). The method adds cluster-driven sampling, formant-based information perturbation, and a cosine-similarity term to preserve emotional information while reducing speaker information (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

This method is summarized as [[self-supervised-emotion-disentanglement]], because the key idea is to preserve emotion while suppressing speaker leakage without relying only on explicit speaker-label adversarial training (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

The TTS system uses FastSpeech 2 with an emotion embedding from the student encoder and a speaker embedding for target speaker characteristics (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). The paper also proposes a dual conditioning transformer to fuse speaker and emotion information into the acoustic model (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## Evaluation

DiEmo-TTS evaluates naturalness, speaker similarity, and emotion similarity with MOS tests, and also reports WER, CER, SECS, and EECS (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). In the cross-speaker emotion transfer ablation table, the full system reports nMOS 4.23, sMOS 3.96, eMOS 4.07, WER 16.16, CER 5.60, SECS 0.8505, and EECS 0.4527 (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## Speaker-Emotion Relevance

DiEmo-TTS is not EVC, but it is strong adjacent evidence for [[speaker-emotion-tradeoff]] because it explicitly studies the tension between preserving target speaker identity and transferring source emotion (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). The paper states that GRL-style explicit speaker disentanglement can create a tradeoff between preserving emotional information and separating speaker identity (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## Caution

The evidence should be marked as adjacent rather than direct EVC evidence because DiEmo-TTS synthesizes speech from text and target speaker conditions rather than converting an input speech waveform to a new emotion (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

## Related pages

- [[cross-speaker-emotion-transfer]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[speaker-disentanglement]]
- [[deep-emotional-features]]
- [[evaluation-metrics-for-voice-conversion]]
- [[self-supervised-emotion-disentanglement]]
- [[speaker-similarity-metrics]]
