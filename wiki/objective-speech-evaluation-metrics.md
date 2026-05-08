# Objective Speech Evaluation Metrics

**Summary**: Compact glossary of objective and semi-objective metrics used across the wiki for speech quality, content preservation, speaker similarity, emotion transfer, and prosody. These metrics are useful for screening systems, but they should not be treated as interchangeable with human perceptual evaluation.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf
- Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf
- Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf

**Last updated**: 2026-05-07

---

## Purpose

This page gives short definitions for recurring metrics used in [[evaluation-metrics-for-voice-conversion]], [[speaker-similarity-metrics]], and [[speaker-identity-evaluation-in-evc]]. The main caution is that a metric only measures closeness under its own representation; Yang et al. 2022 explicitly warns that objective closeness does not guarantee human perception of target similarity (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

## Quality And Naturalness

MOS is a human mean-opinion score, usually used for speech naturalness or quality on a 1-to-5 scale (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). pMOS and QMOS are predicted or model-based quality proxies, while UTMOS and DNSMOS are non-intrusive automatic quality estimators used in recent emotional speech generation and EVC work (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf; source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf; source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

CMOS compares relative quality between systems, and MUSHRA is a multi-stimulus subjective evaluation method used by some speech synthesis papers for naturalness or emotional similarity (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf; source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Content Preservation

WER and CER measure word and character error rates from ASR output, so they are content-preservation or intelligibility proxies rather than direct quality or speaker metrics (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf; source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). PER is a phoneme error rate used similarly when phoneme-level content preservation is evaluated (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

## Spectral And Prosody Metrics

MCD measures mel-cepstral distortion and is mainly a spectral-distance metric (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf; source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). F0 RMSE, log-F0 RMSE, VDE, GPE, FFE, and PCC measure pitch or voicing-related behavior, so they are important for emotional and expressive conversion where pitch carries emotion and naturalness (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf; source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

DDUR measures duration distortion and is relevant when a system changes rhythm or speaking rate rather than only frame-level spectrum (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Speaker Metrics

EER is used in Emo-StarGAN as an anonymisation metric; higher EER means the speaker verifier has more difficulty linking converted speech to the original speaker (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). Speaker classification accuracy measures whether a classifier recognizes the intended or original speaker, depending on the task setup (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf; source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

SECS and x-vector or d-vector cosine similarity are embedding-based speaker-similarity measures, while sMOS and SMOS are subjective speaker-similarity ratings (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf; source: Didi+et+al.pdf). These metrics should be read through [[speaker-similarity-metrics]], because anonymisation, source-speaker preservation, and target-speaker similarity are different speaker-side goals.

## Emotion Metrics

SER accuracy, emotion conversion accuracy, emotion retrieval accuracy, EECS, eMOS, eMOC, emotion2vec similarity, and classifier probabilities are emotion-side proxies used across EVC, SEC, and emotional TTS papers (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf; source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

These metrics are especially risky when the same family of representation is used for training, control, and evaluation. EmoVoice reports that emotion2vec can correlate well at system level while showing much weaker sentence-level agreement with human ratings, so automatic emotion metrics should be paired with listening tests when making strong claims about perceived emotion (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Tradeoff Use

For the [[speaker-emotion-tradeoff]], the strongest metric sets report content, speaker, and emotion axes together rather than optimizing one axis alone (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf; source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). A single aggregate score can hide emotion-specific failures, speaker drift, or content degradation, so metric tables should be read as a bundle rather than as a leaderboard (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[evaluation-metrics-for-voice-conversion]]
- [[speaker-similarity-metrics]]
- [[speaker-identity-evaluation-in-evc]]
- [[speaker-emotion-tradeoff]]
- [[ser-perceptual-loss]]
- [[emotion2vec]]
- [[f0-pitch-contour-in-voice-conversion]]

