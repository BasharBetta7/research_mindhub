# Speaker Disentanglement

**Summary**: Speaker disentanglement means removing speaker identity from the content representation while preserving the information needed for reconstruction or conversion. AutoVC studies this through bottleneck size and speaker classification accuracy.

**Sources**:
- Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

In AutoVC, speaker disentanglement means the content embedding does not contain information about the source speaker (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). The paper evaluates this by training a speaker classifier on the content code, where higher classification accuracy indicates poorer disentanglement (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Mechanisms

[[autovc]] relies on [[information-bottleneck-for-voice-conversion]] to remove speaker information from the content code (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). [[starganv2-vc]] uses adversarial and perceptual losses, including [[adversarial-source-classifier-loss]], to improve target speaker similarity in generated speech (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

In emotion-preserving anonymisation, speaker disentanglement is connected to the [[speaker-emotion-tradeoff]], because removing or changing speaker identity should not erase emotion cues (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[autovc]]
- [[information-bottleneck-for-voice-conversion]]
- [[adversarial-source-classifier-loss]]
- [[voice-conversion]]
- [[speaker-emotion-tradeoff]]
