# ASR Speech Consistency Loss

**Summary**: ASR speech consistency loss preserves linguistic content by comparing source and converted speech features from a pretrained ASR model. In StarGANv2-VC, removing this loss sharply hurts intelligibility.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

ASR speech consistency loss compares intermediate convolutional features from a pretrained joint CTC-attention VGG-BLSTM ASR network between the source and converted mel-spectrograms (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The paper uses the output before the LSTM layers as the linguistic feature representation (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Evidence

The ablation study reports that removing the ASR consistency loss increases CER from 12.55% to 30.34%, while pMOS and speaker classification accuracy remain close to the full model (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). This supports the interpretation that the ASR loss is especially important for preserving linguistic content in [[starganv2-vc]] (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Related pages

- [[starganv2-vc]]
- [[evaluation-metrics-for-voice-conversion]]
- [[non-parallel-voice-conversion]]
