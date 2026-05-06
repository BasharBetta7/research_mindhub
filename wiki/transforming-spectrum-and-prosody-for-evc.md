# Transforming Spectrum And Prosody For EVC

**Summary**: Zhou et al. 2020 proposes a non-parallel emotional voice conversion framework that converts both spectrum and prosody with CycleGAN. The paper uses continuous wavelet transform to model F0 across multiple temporal scales.

**Sources**:
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf

**Last updated**: 2026-05-06

---

## Core idea

The paper proposes a parallel-data-free emotional voice conversion framework that maps speech from one emotion to another while preserving linguistic information and speaker identity (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). It uses CycleGAN to convert spectral features and prosodic F0 features between emotion domains using non-parallel training data (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

The paper argues that emotional voice conversion should transform both spectrum and prosody because emotion is supra-segmental and hierarchical in nature (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). This motivates [[spectrum-prosody-conversion]] rather than only frame-level spectral mapping (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## F0 modelling

The authors use [[cwt-f0-modelling]] to decompose F0 into 10 temporal scales before CycleGAN conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). Lower CWT scales capture short-term variations, while higher scales capture longer-term prosodic variations (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Training strategy

The paper compares joint and separate training of spectrum and prosody conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). [[separate-vs-joint-prosody-training]] is a key finding: separate training performs better than joint training in both objective and subjective evaluations (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Results and limitations

CycleGAN-Separate reports better overall MCD than CycleGAN-Joint, 8.71 dB versus 10.23 dB, in the paper's objective comparison (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). CWT-based F0 conversion improves overall RMSE over the LG-based F0 baseline, 63.03 Hz for separate training versus 70.62 Hz for the baseline, and improves PCC from 0.72 to 0.76 (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

The listening tests strongly prefer separate training over joint training, with preference scores of 93.6% for neutral-to-angry and 96.5% for neutral-to-surprise (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). A limitation is that experiments use a small single-speaker emotional corpus and only 45 source plus 45 target non-parallel utterances for training, so generalization across speakers and languages is not established (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Related pages

- [[cyclegan-evc]]
- [[cwt-f0-modelling]]
- [[spectrum-prosody-conversion]]
- [[separate-vs-joint-prosody-training]]
- [[emotional-speech-conversion]]
- [[non-parallel-voice-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
