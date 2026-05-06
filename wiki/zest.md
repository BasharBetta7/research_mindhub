# ZEST

**Summary**: ZEST is a zero-shot audio-to-audio emotion style transfer system with explicit speaker disentanglement. It is important for the wiki because it measures emotion transfer, content preservation, and speaker preservation across same-speaker, different-speaker, unseen-emotion, and unseen-speaker settings.

**Sources**:
- Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf

**Last updated**: 2026-05-06

---

## Task

ZEST stands for zero-shot emotion style transfer and performs audio-to-audio emotion transfer from a target reference utterance to a source utterance (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). The intended output preserves the source speaker and source linguistic content while adopting the target reference emotion (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## Decomposition

ZEST decomposes speech into HuBERT semantic content tokens, an emotion-agnostic speaker representation, a speaker-agnostic emotion representation, and a predicted F0 contour before neural vocoder synthesis (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). The speaker representation is derived from ECAPA-TDNN x-vectors and trained with emotion-adversarial learning, while the emotion representation uses a wav2vec 2.0-based emotion classifier with speaker-adversarial learning (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

The system predicts F0 from the source content, speaker representation, and target emotion embedding, then uses a HiFi-GAN decoder for waveform generation (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). This makes ZEST a useful source for [[f0-pitch-contour-in-voice-conversion]], because F0 is treated as an explicit prosodic bridge between emotion transfer and speaker-preserving synthesis (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## Evaluation settings

The paper evaluates same-source same-target speaker, same-source different-target speaker, different-source same-target speaker, different-source different-target speaker, unseen target emotion, and unseen source speaker settings (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). It trains on ESD and tests zero-shot generalization with CREMA-D emotions for unseen target emotion and TIMIT speakers for unseen source speaker (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

The objective evaluation reports character error rate for content preservation, emotion conversion accuracy for target emotion transfer, and speaker classification accuracy for source speaker preservation (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). The subjective evaluation reports MOS for quality, emotion-similarity MOS, and speaker-similarity MOS (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## Results

ZEST improves emotion transfer accuracy over the VAWGAN and Polyak-style baselines in the reported conversion settings while keeping speaker classification accuracy high for source-speaker preservation (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). In the same-speaker same-target setting, the paper reports emotion accuracy of 69.0 for ZEST compared with 41.4 for VAWGAN and 36.4 for the Polyak baseline, while speaker accuracy is 99.4 for ZEST (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

The ablations show that removing adversarial disentanglement or removing F0 prediction weakens the system relative to full ZEST, which supports the paper's claim that speaker-emotion disentanglement and pitch prediction matter for zero-shot emotion transfer (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). The unseen-speaker condition has weaker subjective speaker similarity than easier settings, so ZEST is strong evidence for the problem but not evidence that zero-shot speaker preservation is solved (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## Tradeoff relevance

ZEST is direct evidence for [[speaker-emotion-tradeoff]] because it optimizes and evaluates speaker preservation and emotion transfer at the same time (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). It is also a strong source for [[speaker-identity-evaluation-in-evc]] because it includes both objective speaker classification and subjective speaker-similarity MOS (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## Related pages

- [[zero-shot-audio-to-audio-emotion-transfer]]
- [[speaker-disentanglement]]
- [[ssl-disentanglement-for-sec]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[f0-pitch-contour-in-voice-conversion]]
- [[discrete-speech-units-for-evc]]
- [[evaluation-metrics-for-voice-conversion]]
