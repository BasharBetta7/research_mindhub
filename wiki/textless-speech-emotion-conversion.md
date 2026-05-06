# Textless Speech Emotion Conversion

**Summary**: Kreuk et al. 2022 presents a textless speech emotion conversion pipeline that translates discrete speech units and predicts emotion-conditioned prosody. The paper is foundational for EVC systems that separate content units, F0, duration, speaker identity, and emotion.

**Sources**:
- Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf

**Last updated**: 2026-05-06

---

## Task

The paper defines speech emotion conversion as changing perceived emotion while preserving lexical content and speaker identity (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). It is textless because the method operates on learned speech units instead of requiring transcripts or phoneme labels at conversion time (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Decomposition

The model decomposes speech into discrete HuBERT content units, duration, F0, speaker identity, and emotion label (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). It translates source content units into target-emotion units with a sequence-to-sequence Transformer, predicts target prosody, and synthesizes speech with a HiFi-GAN generator conditioned on the decomposed representations (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

The translated discrete units can insert, remove, or substitute non-verbal vocalization cues such as laughter or yawning, which gives the model an emotion-conversion route beyond frame-level spectral conversion (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). This makes the paper important for [[discrete-speech-units-for-evc]] and [[textless-emotion-conversion]] (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## F0 and duration

The system predicts duration and F0 as separate prosody variables conditioned on target emotion and translated units (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). F0 targets are extracted with YAAPT, normalized per speaker, discretized into bins, and decoded back into a pitch contour during synthesis (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

The ablation table shows that changing only the emotion label gives weak emotion conversion, adding F0 helps, adding duration helps more, and translating the discrete units plus predicting prosody gives much stronger emotion recognition results (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). This is direct evidence that emotional conversion is not only a label-control problem; it also depends on prosody and unit-level speech events (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Data and evaluation

The paper trains and evaluates mainly on EmoV, an emotional speech dataset based on CMU Arctic-style utterances with multiple speakers and emotions (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). It also reports out-of-domain conversion on LibriSpeech speech, showing that the textless decomposition can operate beyond the acted emotional training set (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

The paper evaluates subjective quality with MOS, perceived emotion with emotion mean-opinion classification, and lexical preservation with ASR-based WER and PER (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). The reported out-of-domain LibriSpeech conversion has average emotion mean-opinion classification of 82.25%, MOS of 3.69, and WER of 27.92 (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Speaker identity caveat

The paper uses a fixed speaker lookup representation, which supports quality for known speakers but limits generalization to unseen speakers (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). The authors report that a d-vector alternative retained source-emotion prosody and gave inferior disentanglement, which is important evidence that speaker representations can leak emotion-related behavior (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Related pages

- [[textless-emotion-conversion]]
- [[discrete-speech-units-for-evc]]
- [[f0-pitch-contour-in-voice-conversion]]
- [[duration-flexible-evc]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[evaluation-metrics-for-voice-conversion]]
