# Discrete Speech Units For EVC

**Summary**: Discrete speech units represent speech content with learned unit sequences rather than text or phonemes. They support alignment-free, textless, and zero-shot emotional voice conversion by separating content-like information from prosody, speaker, and emotion controls.

**Sources**:
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf
- Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf

**Last updated**: 2026-05-06

---

## Definition

Discrete speech units are learned symbolic representations extracted from self-supervised speech models or codec-like models (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). In EVC, they can represent content without requiring transcripts or forced alignment (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Use in DurFlex-EVC

[[durflex-evc]] uses HuBERT units as targets for a unit aligner and derives unit durations by deduplicating consecutive predicted units (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). This supports [[duration-flexible-evc]] without a text pipeline (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Relation to PFlow-VC

[[pflow-vc]] also uses discrete representations, but with a split between HuBERT semantic tokens and discrete pitch tokens from a pitch VQ-VAE (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). This shows a broader trend: discrete tokens can represent content and prosody separately.

## Textless emotion conversion

[[textless-speech-emotion-conversion]] uses HuBERT discrete units as textless content symbols and translates those units toward a target emotion with a sequence-to-sequence Transformer (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). This is stronger than treating units as fixed content only, because translated units can reflect emotion-related speech events such as non-verbal vocalizations (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Zero-shot emotion transfer

[[zest]] uses HuBERT semantic tokens from the source utterance as the content stream for zero-shot audio-to-audio emotion transfer (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). In that design, the units help preserve source lexical content while target emotion and source speaker information are supplied by separate representations (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

## Related pages

- [[durflex-evc]]
- [[pflow-vc]]
- [[duration-flexible-evc]]
- [[pitch-conditioned-flow-matching]]
- [[non-parallel-voice-conversion]]
- [[textless-speech-emotion-conversion]]
- [[textless-emotion-conversion]]
- [[zest]]
- [[zero-shot-audio-to-audio-emotion-transfer]]
