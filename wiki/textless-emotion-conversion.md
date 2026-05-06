# Textless Emotion Conversion

**Summary**: Textless emotion conversion changes emotional expression without relying on transcripts or phoneme labels at conversion time. Kreuk et al. 2022 shows how this can be done by translating discrete speech units and predicting emotion-conditioned prosody.

**Sources**:
- Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf

**Last updated**: 2026-05-06

---

## Definition

Textless emotion conversion operates on learned speech representations instead of text, phoneme labels, or forced alignments at conversion time (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). It is useful when the conversion system should work directly from speech and preserve lexical content while changing perceived emotion (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Main mechanism

[[textless-speech-emotion-conversion]] uses discrete HuBERT units as content-like symbols, translates those units toward a target emotion, predicts target duration and F0, and synthesizes speech with a neural vocoder (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). This approach links [[discrete-speech-units-for-evc]], [[duration-flexible-evc]], and [[f0-pitch-contour-in-voice-conversion]] into one conversion pipeline (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Why it matters

The paper shows that target emotion is not carried only by a global emotion label, because strong emotion conversion requires changing prosody and sometimes unit-level speech events as well (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). This supports a more critical view of label-conditioned EVC systems: if the acoustic decoder is only given a target label and no mechanism for rhythm, F0, or non-verbal unit changes, it may under-model emotional expression (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Related pages

- [[textless-speech-emotion-conversion]]
- [[discrete-speech-units-for-evc]]
- [[f0-pitch-contour-in-voice-conversion]]
- [[duration-flexible-evc]]
- [[emotional-speech-conversion]]
