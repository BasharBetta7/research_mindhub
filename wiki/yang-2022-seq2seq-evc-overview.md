# Yang 2022 Seq2Seq EVC Overview

**Summary**: Yang et al. 2022 is a compact survey of sequence-to-sequence emotional voice conversion. It argues that Seq2Seq EVC can model duration, rhythm, alignment, spectrum, and prosody jointly, but remains constrained by scarce parallel emotional speech data and difficult evaluation.

**Sources**:
- Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf

**Last updated**: 2026-05-06

---

## Scope

The paper reviews recent [[sequence-to-sequence-emotional-voice-conversion]] work from six angles: motivation, training strategies, model architectures, datasets, model inputs, and evaluation methods (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). It is a survey rather than a new EVC model, so it should be used as synthesis evidence about the field rather than as direct experimental evidence for a new architecture (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

## Main argument

The paper argues that emotional voice conversion aims to convert a source utterance to a target emotion while preserving linguistic information and speaker identity (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). It motivates Seq2Seq EVC by noting that speech rate and rhythm are important factors in emotional conversion, which means output sequences may need different lengths from the input sequence (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

Seq2Seq EVC is presented as useful because it can jointly learn feature mapping, alignment, and duration prediction; reduce mismatch from separately converting spectrum and prosody; and use attention to focus on emotionally emphasized parts of an utterance (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). This connects the paper to [[duration-flexible-evc]] and [[spectrum-prosody-conversion]].

## Surveyed systems

The survey states that, at the time of writing, only six Seq2Seq EVC papers existed (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). The reviewed systems include syllable-level F0 conversion, multitask EVC/TTS, one-to-many expressive VC fine-tuning, two-stage TTS-to-EVC training, and intensity-controlled Seq2Seq EVC systems (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

The paper identifies two emotional intensity-control systems in the reviewed Seq2Seq literature: Choi and Hahn use a weight multiplied with an emotion embedding, while Zhou et al. model intensity through relative attributes without explicit intensity annotation (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). The latter connects directly to [[emovox]] and [[relative-attributes-for-emotion-intensity]].

## Dataset bottleneck

The survey argues that Seq2Seq EVC generally needs large parallel emotional datasets, where the same content is spoken in different emotion categories by the same speaker (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). It also notes that available datasets are either small or have quality limitations, and highlights ESD as clean and parallel but limited to 350 utterances per speaker (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

This makes [[parallel-emotional-speech-data]] a core bottleneck for Seq2Seq EVC. Later systems such as [[durflex-evc]] and [[emoconv-diff]] can be read partly as responses to this bottleneck, because they avoid some dependence on text alignment, forced alignment, or parallel acted data (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

## Evaluation

The survey lists objective metrics used in Seq2Seq EVC, including WER, CER, cosine similarity, MCD, DDUR, VDE, GPE, and FFE (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). It also lists subjective evaluation methods including subjective speech emotion recognition, MOS, ABX tests, and best-worst scaling (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

The paper warns that objective metrics may not be intuitive proxies for human perception, because closeness under a metric does not guarantee that listeners perceive the converted speech as close to the target (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). It also argues that subjective annotations remain the gold standard until more mature automatic evaluation methods become available (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

## Speaker-Emotion Tradeoff Relevance

The paper states the standard EVC goal of changing emotion while preserving linguistic information and speaker identity (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). However, it does not provide a controlled study of how emotion conversion strength affects speaker similarity, so it should not be cited as direct evidence for a quantified [[speaker-emotion-tradeoff]].

## Related pages

- [[sequence-to-sequence-emotional-voice-conversion]]
- [[parallel-emotional-speech-data]]
- [[duration-flexible-evc]]
- [[spectrum-prosody-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emotion-intensity-control]]
- [[emovox]]
- [[relative-attributes-for-emotion-intensity]]
- [[speaker-emotion-tradeoff]]
