# Many-To-Many Voice Conversion

**Summary**: Many-to-many voice conversion supports conversion among multiple source and target speakers. StarGANv2-VC treats each speaker as a domain and uses one generator for multi-speaker conversion.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Many-to-many voice conversion converts among multiple speakers rather than only one source-to-target pair or many sources to one target (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). [[starganv2-vc]] treats each speaker as an individual domain, following the multi-domain design of [[stargan-v2]] (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Training setup

The main StarGANv2-VC experiment trains on 20 selected VCTK speakers and evaluates random source-target speaker pairs across male-to-male, female-to-male, female-to-female, and male-to-female conversion directions (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

[[autovc]] evaluates traditional many-to-many conversion among seen speakers and also extends the setting to [[zero-shot-voice-conversion]] (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). [[emo-stargan]] is also any-to-many, evaluating conversions across datasets, genders, and accent groups while preserving source emotion (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[voice-conversion]]
- [[non-parallel-voice-conversion]]
- [[starganv2-vc]]
- [[autovc]]
- [[emo-stargan]]
