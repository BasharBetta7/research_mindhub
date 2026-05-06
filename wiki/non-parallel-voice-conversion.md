# Non-Parallel Voice Conversion

**Summary**: Non-parallel voice conversion trains without paired source and target utterances. StarGANv2-VC is designed for unsupervised, non-parallel many-to-many conversion.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf
- Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf
- Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf
- Didi+et+al.pdf

**Last updated**: 2026-05-06

---

## Definition

Non-parallel voice conversion does not require matched utterances between source and target speakers (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). This is useful because parallel utterances are often difficult to obtain and can limit where voice conversion is applicable (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## In StarGANv2-VC

[[starganv2-vc]] trains with source samples, target domains, and style codes rather than paired source-target utterance examples (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). Its objective combines adversarial, style, F0, ASR, norm, and cycle consistency losses to preserve content while moving speaker/style identity toward the target domain (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

[[autovc]] also trains without parallel data by reconstructing each input using a same-speaker reference utterance, while [[emo-stargan]] trains on partially emotion-labelled non-parallel data for emotion-preserving anonymisation (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf; source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

[[transforming-spectrum-and-prosody-for-evc]] uses CycleGAN to learn mappings between emotion domains from non-parallel emotional speech, avoiding time alignment and speech-recognition modules (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

[[deepest]] is framed as a one-to-many emotional style transfer model that does not require parallel training data for the conversion model, although it introduces ESD as a parallel emotional speech dataset (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). [[durflex-evc]] avoids text and forced alignment through discrete speech units, but its experiments are still conducted on ESD (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

[[zhou-2022-evc-theory-esd]] groups non-parallel EVC methods into emotional domain translation, disentanglement between emotional prosody and linguistic content, and leveraging TTS or ASR systems (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). [[sgevc]] fits the disentanglement and generative-modeling line by using separate linguistic, speaker, and emotion variables while reducing labeled-data requirements (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

[[seq2seq-cyclegan-evc]] uses CycleGAN refinement to avoid parallel emotional speech requirements in the refinement stage, but its description of ESD conflicts with the canonical ESD source and should be cited cautiously (source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Related pages

- [[voice-conversion]]
- [[many-to-many-voice-conversion]]
- [[starganv2-vc]]
- [[autovc]]
- [[emo-stargan]]
- [[transforming-spectrum-and-prosody-for-evc]]
- [[cyclegan-evc]]
- [[deepest]]
- [[seen-and-unseen-emotion-transfer]]
- [[durflex-evc]]
- [[discrete-speech-units-for-evc]]
- [[zhou-2022-evc-theory-esd]]
- [[sgevc]]
- [[semi-supervised-evc]]
- [[seq2seq-cyclegan-evc]]
