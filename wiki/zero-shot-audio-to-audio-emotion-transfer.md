# Zero-Shot Audio-To-Audio Emotion Transfer

**Summary**: Zero-shot audio-to-audio emotion transfer converts source speech to match the emotion of a reference audio sample while preserving source content and speaker identity. ZEST is the main wiki source for this setting.

**Sources**:
- Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf

**Last updated**: 2026-05-06

---

## Definition

Zero-shot audio-to-audio emotion transfer uses source speech and a target emotional reference utterance as audio inputs, without requiring the target emotion or source speaker to be seen in the same paired training configuration (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). The goal is to preserve the source speaker and lexical content while transferring emotion from the reference audio (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## ZEST formulation

[[zest]] implements this task with HuBERT content tokens from source speech, source speaker embeddings, target emotion embeddings, F0 prediction, and HiFi-GAN synthesis (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). The method uses adversarial training to make the speaker representation less emotion-dependent and the emotion representation less speaker-dependent (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## Evaluation relevance

This setting is especially useful for [[speaker-identity-evaluation-in-evc]] because the system must be evaluated on at least three axes: emotion transfer to the reference emotion, content preservation from the source utterance, and speaker preservation from the source speaker (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). ZEST evaluates these axes with emotion accuracy, character error rate, speaker classification accuracy, MOS, emotion-similarity MOS, and speaker-similarity MOS (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## Related pages

- [[zest]]
- [[speaker-disentanglement]]
- [[ssl-disentanglement-for-sec]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[zero-shot-voice-conversion]]
