# StarGAN V2

**Summary**: StarGAN v2 is a multi-domain image style transfer GAN that StarGANv2-VC adapts to voice conversion. Its style encoder and mapping network ideas are reused to provide diverse target-domain styles.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Role in StarGANv2-VC

StarGAN v2 uses a single generator and discriminator to generate diverse samples in each domain using domain-specific style vectors from either a style encoder or mapping network (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). [[starganv2-vc]] adopts this architecture for speech by treating each speaker as a domain (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Adaptation to speech

The speech version adds a pretrained JDC F0 extraction network so the generator can receive F0-related features alongside source content and style information (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The speech version also introduces [[adversarial-source-classifier-loss]] and perceptual losses based on F0 and ASR features (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Related pages

- [[starganv2-vc]]
- [[style-encoder]]
- [[mapping-network]]
