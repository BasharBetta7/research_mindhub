# CycleGAN EVC

**Summary**: CycleGAN EVC uses cycle-consistent adversarial learning to map speech features between emotion domains without parallel data. Zhou et al. 2020 applies it to both spectrum and CWT-based F0 prosody conversion.

**Sources**:
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf

**Last updated**: 2026-05-06

---

## Definition

CycleGAN learns forward and inverse mappings between source and target domains using adversarial, cycle-consistency, and identity-mapping losses (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). In emotional voice conversion, the source and target domains are emotion domains from the same speaker rather than speaker domains (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Role in Zhou et al. 2020

Zhou et al. train CycleGAN models for 24-dimensional MCEP spectrum conversion and 10-dimensional CWT-F0 prosody conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). The framework does not require parallel training data, speech recognition, or time-alignment procedures (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

## Related pages

- [[transforming-spectrum-and-prosody-for-evc]]
- [[non-parallel-voice-conversion]]
- [[spectrum-prosody-conversion]]
- [[cwt-f0-modelling]]
