# AutoVC

**Summary**: AutoVC is a non-parallel many-to-many and zero-shot voice conversion model trained with only autoencoder reconstruction losses. Its central idea is that a carefully tuned information bottleneck can preserve content while removing speaker identity.

**Sources**:
- Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Core idea

AutoVC frames [[voice-conversion]] as style transfer, where vocal qualities are treated as style and speakers are treated as domains (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). The model uses an autoencoder with a content encoder, a pretrained speaker encoder, and a decoder, trained only through self-reconstruction losses rather than adversarial or variational objectives (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

During conversion, the content encoder receives source speech, the speaker encoder receives target-speaker reference speech, and the decoder combines source content with target speaker embedding (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). During training, the system reconstructs the input using another utterance from the same speaker as the speaker reference, so it does not require parallel source-target utterances (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Bottleneck

AutoVC's main mechanism is [[information-bottleneck-for-voice-conversion]]: the content code is constrained through channel reduction and temporal downsampling so it keeps speaker-independent information while discarding speaker information (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). The paper argues that a too-wide bottleneck leaks speaker identity, while a too-narrow bottleneck loses content and hurts reconstruction (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Zero-shot conversion

AutoVC supports [[zero-shot-voice-conversion]] by using a pretrained speaker encoder that generalizes to speakers unseen during AutoVC training (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). The speaker encoder is pretrained with GE2E-style speaker verification training on VoxCeleb1 and LibriSpeech, covering 3549 speakers in the paper's implementation (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Evaluation and limitations

AutoVC reports stronger subjective MOS and similarity than StarGAN-VC and Chou et al. 2018 in traditional non-parallel many-to-many conversion (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). The paper also reports competitive zero-shot conversion, but similarity drops most clearly for unseen-to-unseen speaker conversion (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

The method is attractive because it avoids difficult GAN training, but its success depends on choosing a bottleneck that balances reconstruction and [[speaker-disentanglement]] (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). In the later [[starganv2-vc]] paper, AutoVC is used as a baseline and is reported to underperform StarGANv2-VC on MOS, speaker classification accuracy, and CER in that setup (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Related pages

- [[voice-conversion]]
- [[autoencoder-voice-conversion]]
- [[information-bottleneck-for-voice-conversion]]
- [[speaker-disentanglement]]
- [[zero-shot-voice-conversion]]
- [[non-parallel-voice-conversion]]
- [[many-to-many-voice-conversion]]
- [[starganv2-vc]]
