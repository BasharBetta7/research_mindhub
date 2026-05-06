# Voice Conversion

**Summary**: Voice conversion changes speaker identity or speaking style while aiming to preserve linguistic content. StarGANv2-VC frames voice conversion as mel-spectrogram translation between speaker domains.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Voice conversion converts one speaker's voice identity into another while preserving linguistic content (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The paper lists applications including movie dubbing, language learning through cross-language conversion, speaking assistance, and singing conversion (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Approaches

The paper groups recent non-parallel voice conversion methods into autoencoder-based, TTS-based, and GAN-based approaches (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). Autoencoder approaches try to encode speaker-independent information using constraints, GAN approaches use discriminators to push generated speech toward the target speaker, and TTS-based approaches use text labels to synthesize speech from linguistic features (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

[[autovc]] is an [[autoencoder-voice-conversion]] system that uses only reconstruction losses and an information bottleneck, while [[starganv2-vc]] is a GAN-based system with adversarial and perceptual losses (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf; source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). [[emo-stargan]] extends voice conversion toward [[speech-anonymisation]] by preserving source emotion while modifying speaker identity (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## StarGANv2-VC framing

[[starganv2-vc]] performs [[non-parallel-voice-conversion]] by learning a mapping from a source speaker domain to a target speaker domain in mel-spectrogram space (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Related pages

- [[starganv2-vc]]
- [[non-parallel-voice-conversion]]
- [[many-to-many-voice-conversion]]
- [[emotional-speech-conversion]]
- [[autovc]]
- [[emo-stargan]]
- [[speech-anonymisation]]
