# Duration-Flexible EVC

**Summary**: Duration-flexible EVC changes emotional expression while allowing speech duration and rhythm to change. DurFlex-EVC models duration without text or forced alignment.

**Sources**:
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf
- Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Duration-flexible EVC explicitly models duration as part of emotional conversion rather than forcing the output to keep the source timing (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). This matters because rhythm and speaking rate are part of emotional prosody (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf; source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

## DurFlex-EVC approach

[[durflex-evc]] predicts unit sequences and their durations from discrete units, which enables duration control without text or speech-text alignment (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). It uses a stochastic duration predictor and length regulator to expand unit-level representations back to frame level (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Relation to Seq2Seq EVC

[[sequence-to-sequence-emotional-voice-conversion]] also models duration, but usually through attention or alignment behavior (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). Yang et al. 2022 treats the ability to generate different output lengths as a key advantage of Seq2Seq EVC over frame-to-frame conversion (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). DurFlex-EVC is different because it aims for parallel generation and avoids external text alignment (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Related pages

- [[durflex-evc]]
- [[discrete-speech-units-for-evc]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[spectrum-prosody-conversion]]
- [[emotion-intensity-control]]
- [[yang-2022-seq2seq-evc-overview]]
- [[parallel-emotional-speech-data]]
