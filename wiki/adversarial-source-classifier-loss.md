# Adversarial Source Classifier Loss

**Summary**: Adversarial source classifier loss is a StarGANv2-VC loss that pushes converted speech to lose source-speaker identity and match the target domain. The ablation study shows it is crucial for speaker similarity.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Motivation

The authors argue that StarGAN v2's original domain-specific discriminator may fail to capture important domain-specific speech features such as speaker pronunciations (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). They add a source classifier with the same architecture as the discriminator to learn the original domain of converted samples (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Training scheme

When training the classifier, the generator is fixed and the classifier learns to identify the original source domain of converted samples (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). When training the generator, the classifier is fixed and the generator is trained so the classifier predicts the target domain rather than the true source domain (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Evidence

The ablation study reports that removing the adversarial source classifier loss reduces speaker classification accuracy from 96.20% to 63.90%, while pMOS remains similar at 3.98 and CER remains similar at 12.33% (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). This suggests the loss mainly affects speaker identity conversion rather than predicted naturalness or intelligibility in the reported metrics (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

This result is relevant to the [[speaker-emotion-tradeoff]] as background evidence that speaker identity metrics can move independently from other quality metrics, although the StarGANv2-VC ablation does not directly measure emotion preservation (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Related pages

- [[starganv2-vc]]
- [[evaluation-metrics-for-voice-conversion]]
- [[many-to-many-voice-conversion]]
- [[speaker-emotion-tradeoff]]
