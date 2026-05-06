# Mapping Network

**Summary**: The mapping network generates target-domain style codes from random latent vectors. In StarGANv2-VC, it supports diverse conversion without requiring a reference utterance.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Function

In [[starganv2-vc]], the mapping network maps a random latent code and target domain into a style vector (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The latent code is sampled from a Gaussian distribution to provide diverse style representations in each target domain (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Relation to style encoder

The mapping network provides style codes without a reference mel-spectrogram, while the [[style-encoder]] extracts style from a reference mel-spectrogram (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Related pages

- [[starganv2-vc]]
- [[style-encoder]]
- [[stargan-v2]]
