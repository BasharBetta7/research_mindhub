# SSL Disentanglement For SEC

**Summary**: SSL disentanglement for speech emotion conversion uses self-supervised speech models to separate lexical content, speaker identity, and emotion information. Prabhu et al. 2023 applies this idea to in-the-wild arousal conversion.

**Sources**:
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf

**Last updated**: 2026-05-06

---

## Definition

SSL disentanglement for SEC uses pretrained self-supervised speech representations to factor an utterance into separate lexical, speaker, and emotion representations before resynthesis (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

In Prabhu et al. 2023, HuBERT discrete units represent lexical content, WavLM speaker verification embeddings represent speaker identity, and an arousal-conditioned emotion embedding represents emotion (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Why it matters

The approach is important for [[in-the-wild-emotion-conversion]] because non-parallel naturalistic datasets do not provide matched source-target emotional utterances (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

Disentanglement is also central to [[speaker-emotion-tradeoff]] because a system that fails to separate speaker and emotion factors may change speaker identity while trying to change emotion (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Related pages

- [[prabhu-2023-in-the-wild-sec]]
- [[in-the-wild-emotion-conversion]]
- [[speaker-disentanglement]]
- [[speaker-emotion-tradeoff]]
- [[arousal-based-emotion-control]]
