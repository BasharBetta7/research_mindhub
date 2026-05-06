# Sequence-To-Sequence Emotional Voice Conversion

**Summary**: Sequence-to-sequence emotional voice conversion jointly models acoustic mapping and temporal alignment. Yang et al. 2022 surveys this line of work and frames duration, rhythm, parallel data, and evaluation as central issues.

**Sources**:
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf
- Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf
- Didi+et+al.pdf
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf

**Last updated**: 2026-05-06

---

## Motivation

Sequence-to-sequence models with attention can jointly learn feature mapping and alignment, and can predict speech duration at run time (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). Yang et al. 2022 gives the broader survey motivation: speech rate and rhythm are key factors of emotional conversion, so emotional conversion may require output sequences with different lengths from the input (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

[[yang-2022-seq2seq-evc-overview]] summarizes three advantages of Seq2Seq EVC: joint feature mapping/alignment/duration prediction, less mismatch between separately converted spectrum and prosody, and attention over emotionally emphasized utterance regions (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

[[tacotron]] is useful historical background because it shows how sequence-to-sequence attention can map text to acoustic frames in TTS, but it is not an EVC model and should not be cited as emotional conversion evidence (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

## Difference from frame-based EVC

Frame-based emotional voice conversion methods usually convert spectrum or prosody parameters frame by frame and cannot modify speech duration (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). The paper argues that sequence-to-sequence modelling is better suited to jointly transfer spectrum and prosody and reduce mismatch between separately converted features (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

Zhou et al. 2020 is an example of a non-Seq2Seq frame-level approach that improves emotional voice conversion by explicitly converting both spectrum and CWT-based prosody, but it still relies on WORLD features and does not predict duration like Emovox (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf; source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

[[durflex-evc]] addresses the same duration problem from a different direction: it avoids autoregressive Seq2Seq modelling by using discrete units, duration prediction, and parallel generation (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). This makes [[duration-flexible-evc]] a broader category than Seq2Seq EVC.

[[seq2seq-cyclegan-evc]] uses Seq2Seq differently: the Seq2Seq module generates a coarse emotion-aware Mel-spectrogram for long-range temporal modelling, then CycleGAN refines the spectrum for adversarial realism (source: Didi+et+al.pdf). This hybrid method is relevant as an architecture pattern, but its ESD metadata conflict means it should not override the canonical ESD description from [[zhou-2022-evc-theory-esd]] (source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Dataset constraint

Yang et al. 2022 argues that Seq2Seq EVC generally requires large [[parallel-emotional-speech-data]], where the same content appears in different emotion categories by the same speaker (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). This is the main reason the survey treats Seq2Seq EVC as promising but not yet dominant in EVC (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

## Emovox

[[emovox]] is a sequence-to-sequence EVC framework with a recognition encoder and decoder structure, plus explicit emotion and intensity embeddings (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). The paper uses DDUR to evaluate duration conversion, because duration is a relevant output dimension for sequence-to-sequence EVC (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Related pages

- [[emovox]]
- [[yang-2022-seq2seq-evc-overview]]
- [[parallel-emotional-speech-data]]
- [[emotion-intensity-control]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emotional-speech-conversion]]
- [[spectrum-prosody-conversion]]
- [[transforming-spectrum-and-prosody-for-evc]]
- [[durflex-evc]]
- [[duration-flexible-evc]]
- [[discrete-speech-units-for-evc]]
- [[tacotron]]
- [[seq2seq-tts]]
- [[seq2seq-cyclegan-evc]]
- [[seq2seq-cyclegan-refinement]]
