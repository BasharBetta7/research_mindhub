# CWT F0 Modelling

**Summary**: CWT F0 modelling decomposes fundamental frequency into multiple temporal scales. Zhou et al. 2020 uses it to represent emotional prosody more richly than a simple linear F0 transform.

**Sources**:
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf

**Last updated**: 2026-05-06

---

## Definition

Continuous wavelet transform decomposes an F0 contour into temporal scales, allowing short-term and long-term prosodic variations to be represented separately (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). Zhou et al. use 10 discrete CWT scales for F0 modelling in emotional voice conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Preprocessing

Because WORLD-extracted F0 is discontinuous in unvoiced regions, the paper first linearly interpolates unvoiced regions, transforms F0 to logarithmic scale, and normalizes F0 to zero mean and unit variance before CWT decomposition (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Evidence

CWT-based F0 conversion outperforms the baseline LG-based F0 linear transform in objective F0 conversion metrics (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). The overall F0 RMSE improves from 70.62 Hz for the baseline to 63.03 Hz for CycleGAN-Separate, while PCC improves from 0.72 to 0.76 (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Related pages

- [[f0-consistency-loss]]
- [[emotion-intensity-control]]
- [[spectrum-prosody-conversion]]
- [[transforming-spectrum-and-prosody-for-evc]]
