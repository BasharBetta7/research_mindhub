# Discrete Speech Units For EVC

**Summary**: Discrete speech units represent speech content with learned unit sequences rather than text or phonemes. DurFlex-EVC uses them for alignment-free emotional voice conversion.

**Sources**:
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf

**Last updated**: 2026-05-06

---

## Definition

Discrete speech units are learned symbolic representations extracted from self-supervised speech models or codec-like models (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). In EVC, they can represent content without requiring transcripts or forced alignment (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Use in DurFlex-EVC

[[durflex-evc]] uses HuBERT units as targets for a unit aligner and derives unit durations by deduplicating consecutive predicted units (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). This supports [[duration-flexible-evc]] without a text pipeline (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Relation to PFlow-VC

[[pflow-vc]] also uses discrete representations, but with a split between HuBERT semantic tokens and discrete pitch tokens from a pitch VQ-VAE (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). This shows a broader trend: discrete tokens can represent content and prosody separately.

## Related pages

- [[durflex-evc]]
- [[pflow-vc]]
- [[duration-flexible-evc]]
- [[pitch-conditioned-flow-matching]]
- [[non-parallel-voice-conversion]]
