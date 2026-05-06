# Style Encoder

**Summary**: The style encoder extracts a target-domain style code from a reference mel-spectrogram. In StarGANv2-VC, it enables reference-guided speaker or style conversion.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Function

In [[starganv2-vc]], the style encoder takes a reference mel-spectrogram and a target domain and outputs a style code for that domain (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The style encoder uses shared layers across domains followed by a domain-specific projection into the style code (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Use in conversion

The generator receives the style code through adaptive instance normalization in the decoder (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). This lets the target reference utterance influence the converted mel-spectrogram's speaker or style characteristics (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Related pages

- [[starganv2-vc]]
- [[mapping-network]]
- [[emotional-speech-conversion]]
