# F0 Consistency Loss

**Summary**: F0 consistency loss encourages converted speech to preserve the source utterance's normalized pitch contour. StarGANv2-VC uses a pretrained JDC F0 network for this signal.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf

**Last updated**: 2026-05-06

---

## Definition

F0 consistency loss compares the normalized F0 curve of the source mel-spectrogram with the normalized F0 curve of the converted mel-spectrogram (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The paper normalizes absolute F0 values by their temporal mean because male and female speakers have different average F0 ranges (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Role in StarGANv2-VC

[[starganv2-vc]] uses a pretrained JDC F0 extraction network and feeds convolutional F0 features into the generator (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The authors note that removing the F0 loss does not necessarily lower pMOS, speaker classification accuracy, or CER, but they observed unnatural intonation in converted samples without it (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

Zhou et al. show that F0 is also relevant to [[emotion-intensity-control]]: stronger angry and happy conversions tend to have higher F0 values and larger F0 fluctuations, while sad intensity appears less tied to F0 range and more tied to speaking rate in their visual analysis (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

Zhou et al. 2020 model F0 with [[cwt-f0-modelling]], arguing that a single F0 value or simple linear F0 transformation does not characterize hierarchical speech prosody well enough for emotional voice conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Related pages

- [[starganv2-vc]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emotion-intensity-control]]
- [[cwt-f0-modelling]]
