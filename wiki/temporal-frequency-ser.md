# Temporal Frequency SER

**Summary**: Temporal-frequency SER models emotion from both time-domain dynamics and frequency-domain structure. TF-Mamba is the current wiki example, using Mamba state-space modeling in both domains.

**Sources**:
- Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf

**Last updated**: 2026-05-06

---

## Definition

Temporal-frequency SER is speech emotion recognition that explicitly models both temporal evolution and frequency-domain structure in speech features (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The motivation is that emotional speech is carried not only by temporal intensity changes but also by frequency-domain envelope structure related to tone, timbre, pitch, and intonation (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## TF-Mamba example

[[tf-mamba-ser]] implements temporal-frequency SER with a temporal branch and a frequency branch inside a bi-domain State Space Duality block (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The temporal branch captures short-term dependencies in speech embeddings, while the frequency branch uses FFT and adaptive filtering to retain useful low-frequency emotional information and reduce noise (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## Relation to emotional speech generation

Temporal-frequency SER can inform emotional speech generation evaluation because many generation papers rely on SER-derived probabilities, embeddings, or consistency scores (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

This is still proxy evidence: stronger SER accuracy does not automatically prove that a generated or converted sample has the intended emotion for human listeners (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## Related pages

- [[tf-mamba-ser]]
- [[ser-perceptual-loss]]
- [[deep-emotional-features]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emotion2vec]]
