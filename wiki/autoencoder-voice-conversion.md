# Autoencoder Voice Conversion

**Summary**: Autoencoder voice conversion uses an encoder-decoder structure to separate content from speaker/style information. AutoVC is a prominent example that trains only on self-reconstruction losses.

**Sources**:
- Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## General idea

Autoencoder-based voice conversion tries to encode speaker-independent information from speech and decode it with target speaker/style information (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The StarGANv2-VC paper notes that autoencoder methods depend on carefully designed constraints to remove speaker-dependent information (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## AutoVC example

[[autovc]] uses a content encoder, pretrained speaker encoder, and decoder, and trains with self-reconstruction plus content-code reconstruction losses (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). Its core constraint is a carefully tuned [[information-bottleneck-for-voice-conversion]] rather than adversarial training (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Related pages

- [[autovc]]
- [[voice-conversion]]
- [[speaker-disentanglement]]
- [[information-bottleneck-for-voice-conversion]]
