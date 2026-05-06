# Hierarchical Emotion Control

**Summary**: Hierarchical emotion control manipulates emotional expression at multiple linguistic levels, such as utterance, word, and phoneme. Inoue et al. 2025 applies this idea to emotional TTS with hierarchical emotion distributions.

**Sources**:
- Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Definition

Hierarchical emotion control means controlling emotional rendering at more than one temporal or linguistic level, such as the utterance, word, and phoneme levels (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The motivation is that speech emotion is not only a global utterance property: utterance-level prosody, emotionally salient words, and phoneme-level pitch, energy, and duration can all contribute to perceived emotion (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Implementation in Inoue et al. 2025

The paper implements hierarchical control by extracting [[hierarchical-emotion-distribution]] embeddings from reference audio and using them as soft conditions for a diffusion-based emotional TTS model (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The system allows user-driven modification of emotion rendering at utterance, word, or phoneme level during inference (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Relation to intensity control

Hierarchical emotion control is a finer-grained form of [[emotion-intensity-control]] because the intensity variable is not restricted to one scalar for the full utterance (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

This distinction matters for EVC research because utterance-level intensity control may miss localized emotional emphasis, although Inoue et al. 2025 itself is a TTS study rather than an EVC study (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Related pages

- [[hierarchical-emotion-rendering]]
- [[hierarchical-emotion-distribution]]
- [[emotion-intensity-control]]
- [[spectrum-prosody-conversion]]
- [[speaker-emotion-tradeoff]]
