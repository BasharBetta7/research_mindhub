# StarGANv2-VC

**Summary**: StarGANv2-VC is an unsupervised, non-parallel many-to-many voice conversion framework that adapts StarGAN v2 to speech. It combines style-based conversion, F0 conditioning, adversarial source classification, and perceptual consistency losses to improve naturalness and speaker similarity.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Core idea

StarGANv2-VC converts a source speaker's mel-spectrogram into a target speaker domain while preserving linguistic content, using non-parallel data rather than paired utterances (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The model treats each speaker as a domain, adapting [[stargan-v2]] from multi-domain image style transfer to [[many-to-many-voice-conversion]] (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

The framework can use either a [[style-encoder]] with a reference utterance or a [[mapping-network]] with a random latent code to produce target-domain style codes (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The generator receives the source mel-spectrogram, target style code, and F0 features from a pretrained JDC F0 network (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Losses

The model uses adversarial loss, style reconstruction loss, style diversification loss, [[f0-consistency-loss]], [[asr-speech-consistency-loss]], norm consistency loss, cycle consistency loss, and [[adversarial-source-classifier-loss]] (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

The paper presents adversarial source classification as a major addition over the original StarGAN v2 setup, because it gives the generator feedback about source-speaker traits that remain after conversion (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Evaluation

The main experiment trains on 20 selected VCTK speakers and compares StarGANv2-VC with AUTO-VC (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). Subjective evaluation used MOS for naturalness and similarity ratings from online raters, while objective evaluation used pMOS, speaker classification accuracy, and CER (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

StarGANv2-VC reports MOS values around 4.02 to 4.25 across conversion directions, while AUTO-VC reports around 2.17 to 2.86 (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). In objective evaluation, full StarGANv2-VC reports pMOS 3.95, speaker classification accuracy 96.20%, and CER 12.55%, while AUTO-VC reports pMOS 3.43, speaker classification accuracy 50.30%, and CER 47.43% (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Later extension

[[emo-stargan]] extends StarGANv2-VC for [[emotion-preserving-voice-conversion]] in a [[speech-anonymisation]] setting, arguing that vanilla StarGANv2-VC does not preserve source emotion well enough under diverse emotions and acoustic conditions (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Relevance to emotional speech

The authors train additional models on ESD for emotional speech and JVS for falsetto conversion, claiming that the framework can convert plain speech into stylistic speech such as emotional acting or falsetto speech (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). This makes the paper relevant to [[emotional-speech-conversion]], but the stylistic and cross-lingual claims are mainly supported by demos rather than the same full subjective and objective evaluation used for the VCTK experiment (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Related pages

- [[voice-conversion]]
- [[non-parallel-voice-conversion]]
- [[many-to-many-voice-conversion]]
- [[stargan-v2]]
- [[style-encoder]]
- [[mapping-network]]
- [[adversarial-source-classifier-loss]]
- [[f0-consistency-loss]]
- [[asr-speech-consistency-loss]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emotional-speech-conversion]]
- [[emo-stargan]]
- [[emotion-preserving-voice-conversion]]
