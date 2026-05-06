# Separate Vs Joint Prosody Training

**Summary**: Separate versus joint prosody training compares whether spectrum and prosody should be learned together or with separate models. Zhou et al. 2020 finds separate CycleGAN training works better under limited non-parallel data.

**Sources**:
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf

**Last updated**: 2026-05-06

---

## Training strategies

Joint training concatenates 24 MCEPs and 10 CWT-F0 coefficients into one frame-level vector and trains one joint spectrum-prosody CycleGAN (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). Separate training trains one CycleGAN for spectrum conversion and another CycleGAN for prosody conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Results

Separate training reports lower overall MCD than joint training, 8.71 dB versus 10.23 dB (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). Subjective XAB tests also strongly favor separate training over joint training, with preference scores of 93.6% for neutral-to-angry and 96.5% for neutral-to-surprise (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Interpretation

The authors argue that joint training ties CWT-F0 coefficients to spectral features at the frame level, implicitly assuming prosody is content-dependent (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). With only 45 non-parallel source and 45 non-parallel target utterances, the joint model may not generalize emotional mapping well to unseen content, while separate prosody training can learn a more content-independent emotional mapping (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Related pages

- [[transforming-spectrum-and-prosody-for-evc]]
- [[spectrum-prosody-conversion]]
- [[cwt-f0-modelling]]
- [[non-parallel-voice-conversion]]
