# SSL Disentanglement For SEC

**Summary**: SSL disentanglement for speech emotion conversion uses self-supervised speech models to separate lexical content, speaker identity, and emotion information. Prabhu et al. 2023 applies this idea to in-the-wild arousal conversion.

**Sources**:
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf
- Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf
- Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf

**Last updated**: 2026-05-06

---

## Definition

SSL disentanglement for SEC uses pretrained self-supervised speech representations to factor an utterance into separate lexical, speaker, and emotion representations before resynthesis (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

In Prabhu et al. 2023, HuBERT discrete units represent lexical content, WavLM speaker verification embeddings represent speaker identity, and an arousal-conditioned emotion embedding represents emotion (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Why it matters

The approach is important for [[in-the-wild-emotion-conversion]] because non-parallel naturalistic datasets do not provide matched source-target emotional utterances (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

Disentanglement is also central to [[speaker-emotion-tradeoff]] because a system that fails to separate speaker and emotion factors may change speaker identity while trying to change emotion (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

[[zest]] follows the same high-level decomposition pattern with HuBERT content tokens, ECAPA-derived speaker representations, wav2vec 2.0 emotion representations, and explicit adversarial losses to reduce speaker-emotion leakage (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). [[diffevc]] uses pretrained speaker and emotion encoders plus [[mutual-information-disentanglement]], showing a related but diffusion-based route to separating speaker and emotion factors (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Related pages

- [[prabhu-2023-in-the-wild-sec]]
- [[in-the-wild-emotion-conversion]]
- [[speaker-disentanglement]]
- [[speaker-emotion-tradeoff]]
- [[arousal-based-emotion-control]]
- [[zest]]
- [[diffevc]]
- [[mutual-information-disentanglement]]
