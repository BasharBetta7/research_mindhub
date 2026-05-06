# Zhou 2022 EVC Theory ESD

**Summary**: Zhou et al. 2022 reviews emotional voice conversion methods and emotional speech databases, then releases ESD as a bilingual parallel emotional speech dataset. It is a foundational source for EVC definitions, dataset limitations, spectrum-prosody modelling, and ESD-based evaluation.

**Sources**:
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf

**Last updated**: 2026-05-06

---

## Scope

The paper defines emotional voice conversion as converting the emotional state of an utterance while preserving linguistic information and speaker identity (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). It reviews parallel EVC, non-parallel EVC, emotional speech databases, and then introduces [[esd-dataset]] as a reference database for EVC research (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Method taxonomy

For parallel EVC, the paper describes a typical pipeline of feature extraction, frame alignment, and feature mapping, with spectral features such as MCC, LPCC, and LSF and prosodic features such as pitch, energy, and duration (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). It argues that both spectral and prosodic components need attention because emotion is expressed through coupled spectrum and prosody rather than spectrum alone (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

For non-parallel EVC, the paper groups methods into emotional domain translation, disentanglement between emotional prosody and linguistic content, and leveraging TTS or ASR systems (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). CycleGAN-based methods use adversarial, cycle-consistency, and identity-mapping losses to learn emotion-domain mappings without parallel utterances (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## ESD contribution

The paper releases ESD with 10 native English speakers and 10 native Chinese speakers, 350 parallel utterances per speaker per emotion, and five emotion categories: neutral, happy, angry, sad, and surprise (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). It reports more than 29 hours of controlled studio speech and frames ESD as suitable for multi-speaker, cross-lingual, and speaker-independent EVC studies (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

The paper partitions each speaker-emotion set into 20 evaluation utterances, 30 test utterances, and 300 training utterances (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). It reports F0 statistics by language, emotion, and gender, showing that happy and surprise generally have higher F0 mean and variance, while neutral and sad have lower F0 values (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Reference EVC experiments

The paper implements CycleGAN-EVC and VAWGAN-EVC on one male ESD speaker for neutral-to-angry, neutral-to-happy, neutral-to-sad, and neutral-to-surprise conversion (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). It reports that CycleGAN-EVC obtains lower MCD than VAWGAN-EVC in all four conversion pairs and better MOS speech quality, while VAWGAN-EVC is faster to train and supports many-to-many emotion control more naturally (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Tradeoff relevance

This source is foundational for [[speaker-emotion-tradeoff]] because it defines EVC as an emotion change that must preserve speaker identity and linguistic content (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). However, its reference experiments do not provide a controlled speaker-emotion Pareto frontier; the MOS quality test includes speaker identity preservation as part of overall quality, but the paper does not report a separate speaker-similarity metric for the EVC experiments (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Related pages

- [[esd-dataset]]
- [[emotional-speech-databases]]
- [[emotional-speech-conversion]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[spectrum-prosody-conversion]]
- [[f0-pitch-contour-in-voice-conversion]]
- [[parallel-emotional-speech-data]]
- [[non-parallel-voice-conversion]]
- [[cyclegan-evc]]
