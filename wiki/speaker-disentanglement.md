# Speaker Disentanglement

**Summary**: Speaker disentanglement means removing speaker identity from the content representation while preserving the information needed for reconstruction or conversion. AutoVC studies this through bottleneck size and speaker classification accuracy.

**Sources**:
- Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf
- Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf
- Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf
- Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf
- Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf

**Last updated**: 2026-05-06

---

## Definition

In AutoVC, speaker disentanglement means the content embedding does not contain information about the source speaker (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). The paper evaluates this by training a speaker classifier on the content code, where higher classification accuracy indicates poorer disentanglement (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Mechanisms

[[autovc]] relies on [[information-bottleneck-for-voice-conversion]] to remove speaker information from the content code (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). [[starganv2-vc]] uses adversarial and perceptual losses, including [[adversarial-source-classifier-loss]], to improve target speaker similarity in generated speech (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

In emotion-preserving anonymisation, speaker disentanglement is connected to the [[speaker-emotion-tradeoff]], because removing or changing speaker identity should not erase emotion cues (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

[[ssl-disentanglement-for-sec]] uses pretrained SSL encoders for a different disentanglement route: HuBERT units for lexical content, WavLM speaker verification embeddings for speaker identity, and arousal embeddings for emotion (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

[[diffevc]] explicitly reduces dependence between speaker and emotion representations with [[mutual-information-disentanglement]], while preserving speaker and emotion information through auxiliary supervised objectives (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). [[zest]] uses adversarial training in both directions: an emotion-agnostic speaker encoder and a speaker-agnostic emotion encoder (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

[[textless-speech-emotion-conversion]] provides a cautionary example because a d-vector speaker representation retained source-emotion prosody and produced inferior disentanglement compared with the fixed speaker lookup representation used in the paper (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

[[sgevc]] records another disentanglement method: speaker identity is an observed conditioning variable, emotion is a categorical latent variable sampled with Gumbel-Softmax, and linguistic content is represented by a separate latent variable tied to text conditioning (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). This is useful for [[speaker-emotion-tradeoff]] method design, but the paper does not directly test whether stronger target emotion causes speaker drift (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Related pages

- [[autovc]]
- [[information-bottleneck-for-voice-conversion]]
- [[adversarial-source-classifier-loss]]
- [[voice-conversion]]
- [[speaker-emotion-tradeoff]]
- [[ssl-disentanglement-for-sec]]
- [[prabhu-2023-in-the-wild-sec]]
- [[diffevc]]
- [[mutual-information-disentanglement]]
- [[zest]]
- [[zero-shot-audio-to-audio-emotion-transfer]]
- [[textless-speech-emotion-conversion]]
- [[sgevc]]
- [[semi-supervised-evc]]
