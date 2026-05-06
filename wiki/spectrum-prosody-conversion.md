# Spectrum Prosody Conversion

**Summary**: Spectrum-prosody conversion transforms both spectral envelope and prosodic features during voice conversion. In emotional voice conversion, this matters because emotion is expressed through both timbre-like and prosodic cues.

**Sources**:
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf
- Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf
- Didi+et+al.pdf

**Last updated**: 2026-05-06

---

## Definition

Spectrum-prosody conversion converts spectral features and prosodic features rather than treating prosody as fixed or speaker-independent (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). This is important for emotional voice conversion because emotion is conveyed by prosodic features such as pitch, intensity, and speaking rate (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Zhou et al. 2020

Zhou et al. use 24-dimensional MCEPs for spectrum conversion and 10-scale CWT-F0 features for prosody conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). Aperiodicity is copied from the source during conversion in their WORLD-based synthesis pipeline (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Relation to intensity

The later Emovox paper also argues against simple frame-level conversion for emotional speech because emotion has supra-segmental prosodic dynamics (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). This supports treating spectrum and prosody as coupled research concerns even when a model architecture differs, such as [[cyclegan-evc]] versus [[sequence-to-sequence-emotional-voice-conversion]] (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf; source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

Yang et al. 2022 gives a survey-level statement of the same problem: frame-based mapping can be insufficient because emotion is supra-segmental and depends on multiple signal attributes across spectrum and prosody (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). It also argues that separately mapping spectrum and prosody can create mismatches, which motivates joint Seq2Seq modelling (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

[[zhou-2022-evc-theory-esd]] gives the canonical theory statement: emotion is inherently supra-segmental and complex, involving both spectrum and prosody, so frame-wise spectral mapping alone is insufficient for EVC (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). [[seq2seq-cyclegan-evc]] records a hybrid method response to this issue, using Seq2Seq for temporal modelling and CycleGAN for Mel-spectrogram refinement (source: Didi+et+al.pdf).

[[emoconv-diff]] provides related evidence from arousal conversion: its qualitative analysis links high-arousal converted speech with higher pitch mean and pitch variability (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This supports the idea that emotional conversion should be checked through prosodic cues, not only spectral reconstruction (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

[[durflex-evc]] explicitly evaluates pitch, energy, and duration and reports better average prosody errors than compared EVC baselines (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). [[pflow-vc]] focuses on expressive VC by discretizing speaker-normalized pitch and conditioning a flow matching decoder on pitch tokens (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

[[daisy-tts]] makes the prosody-emotion connection explicit in TTS by learning emotion-separable prosody embeddings from mel-spectrogram, pitch contour, and energy contour features (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). [[diemo-tts]] adds a speaker-disentanglement caution: some prosodic features are associated with speaker identity, which makes clean separation of speaker identity and emotion-related prosody difficult (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

[[f0-pitch-contour-in-voice-conversion]] collects the specific role of pitch contour extraction in naturalness, emotion intensity, and speaker identity leakage.

## Related pages

- [[transforming-spectrum-and-prosody-for-evc]]
- [[cwt-f0-modelling]]
- [[separate-vs-joint-prosody-training]]
- [[emotion-intensity-control]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[emoconv-diff]]
- [[arousal-based-emotion-control]]
- [[durflex-evc]]
- [[duration-flexible-evc]]
- [[pflow-vc]]
- [[pitch-conditioned-flow-matching]]
- [[yang-2022-seq2seq-evc-overview]]
- [[daisy-tts]]
- [[prosody-embedding-decomposition]]
- [[diemo-tts]]
- [[cross-speaker-emotion-transfer]]
- [[f0-pitch-contour-in-voice-conversion]]
- [[zhou-2022-evc-theory-esd]]
- [[seq2seq-cyclegan-evc]]
- [[seq2seq-cyclegan-refinement]]
