# Emotional Speech Databases

**Summary**: Emotional speech databases provide the recordings used to train and evaluate emotional voice conversion and emotional speech generation systems. Zhou et al. 2022 surveys their limitations and positions ESD as a benchmark for EVC.

**Sources**:
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf

**Last updated**: 2026-05-06

---

## Why databases matter

Emotional voice conversion depends strongly on the emotional speech data used for training and evaluation (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). The paper argues that EVC needs databases with sufficient lexical variability, language variability, speaker variability, controlled confounding factors, and good recording quality (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Common limitations

Many emotional speech databases have limited lexical variability, limited speaker variability, non-ideal recording conditions, or confounding factors such as accent, laughter, sighs, overlapping speech, and external noise (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). These limitations matter more for speech synthesis and EVC than for speech emotion recognition, because synthesis quality is sensitive to recording quality and lexical coverage (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## ESD's role

[[esd-dataset]] was designed as a controlled acted emotional speech database with parallel utterances, bilingual coverage, multiple speakers, and studio recording conditions (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). It is especially useful for [[speaker-emotion-tradeoff]] research because it supports same-content comparisons across emotion categories while preserving speaker identity as a controlled factor (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Related pages

- [[esd-dataset]]
- [[zhou-2022-evc-theory-esd]]
- [[parallel-emotional-speech-data]]
- [[emotional-speech-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
