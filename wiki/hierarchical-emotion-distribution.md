# Hierarchical Emotion Distribution

**Summary**: A hierarchical emotion distribution is a soft emotion-intensity representation defined across utterance, word, and phoneme segments. Inoue et al. 2025 uses it to condition emotional TTS and to support fine-grained emotion rendering control.

**Sources**:
- Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Definition

In Inoue et al. 2025, a hierarchical emotion distribution is a set of emotion-intensity distributions extracted at utterance, word, and phoneme levels (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The utterance-level distribution is replicated to phoneme length, and the word-level distribution is adjusted to match the corresponding phonemes before the levels are combined for TTS conditioning (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Extractor

The extractor segments audio and transcript information into utterance, word, and phoneme segments, then predicts emotion distributions for each segment level (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The paper evaluates feature choices including OpenSMILE, WavLM, and HuBERT, and reports that combining self-supervised features with OpenSMILE can improve different parts of the control problem (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The paper compares Speech Emotion Recognizer and Emotion Presence Recognizer classifier modules for extracting the distributions (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Related pages

- [[hierarchical-emotion-rendering]]
- [[hierarchical-emotion-control]]
- [[emotion-intensity-control]]
- [[self-supervised-emotion-disentanglement]]
