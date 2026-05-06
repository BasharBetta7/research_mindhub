# Speaker Identity Evaluation In EVC

**Summary**: Speaker identity evaluation in emotional voice conversion measures whether converted speech still sounds like the intended speaker while emotion is changed or preserved. Existing sources evaluate this with EER, speaker similarity scores, speaker classification, sMOS, and SECS, but they do not yet provide a controlled speaker-emotion Pareto curve.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf
- Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf

**Last updated**: 2026-05-06

---

## Definition

Speaker identity evaluation in EVC asks whether emotion conversion preserves, changes, or anonymises speaker identity as intended (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). This is the measurement side of the [[speaker-emotion-tradeoff]]: a system may improve emotion transfer or preservation while harming speaker similarity, anonymisation, or intelligibility (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

[[speaker-similarity-metrics]] separates the speaker-side measures used across the wiki, because anonymisation EER, speaker classification accuracy, sMOS, SMOS, and SECS answer related but different questions (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Direct evidence

[[emo-stargan]] gives the clearest direct tradeoff evidence because it reports emotion preservation metrics together with anonymisation EER (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). Emo-StarGAN improves aggregate emotion preservation while EER remains almost unchanged at 49.63 versus 49.64, suggesting no measurable anonymisation penalty in that setup (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

[[durflex-evc]] reports speaker similarity and emotion metrics together, including subjective sMOS and objective SECS, ECA, and EECS (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). It therefore studies whether a stronger duration/prosody EVC system preserves speaker identity, but it does not sweep a control variable to show how emotion strength affects speaker similarity (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

[[pflow-vc]] is expressive VC rather than dedicated EVC, but it evaluates speaker similarity and emotion consistency in the same system (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). Its ablation shows that removing [[time-varying-timbre-tokens]] lowers SECS from 0.920 to 0.877 and gives a large negative speaker-similarity CMOS, making it relevant to timbre preservation under expressive conversion (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Partial evidence

[[emoconv-diff]] explicitly aims to preserve speaker identity while converting arousal, and it uses a pretrained speaker verification model as a speaker encoder (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). Its reported evaluation focuses on SER arousal error and DNSMOS rather than a detailed speaker identity analysis, so it is weaker evidence for speaker drift (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

[[prabhu-2023-in-the-wild-sec]] uses a WavLM speaker verification embedding as the speaker representation while converting arousal, so it explicitly designs for speaker preservation (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf). However, its reported evaluation focuses on SER arousal errors and WVMOS, so it does not directly measure speaker similarity after conversion (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

[[einet]] includes an identity maintainer to reduce speaker identity loss during controllable EVC, especially by constraining F0 and voicing behavior (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf). Its main reported table still lacks standard speaker-similarity metrics such as SECS, sMOS, or EER, so it is partial rather than complete evidence for identity preservation (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

[[starganv2-vc]] contributes speaker-identity evidence through speaker classification and source-classifier ablations, but its main reported emotional conversion evidence is weaker than its speaker-conversion evaluation (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). Removing the adversarial source classifier reduces speaker classification accuracy from 96.20% to 63.90% while pMOS and CER stay similar, showing that speaker identity metrics can move independently from naturalness and intelligibility metrics (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

[[clapfm-evc]] is direct EVC evidence for flexible emotion control, but its main reported tables use MCD, RMSE, CER, UTMOS, nMOS, EECS, and eMOS rather than explicit speaker-similarity metrics such as SECS, sMOS, or EER (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). It should therefore be treated as partial evidence for speaker identity preservation until speaker-side evaluation is added or found (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

[[diemo-tts]] is adjacent TTS evidence rather than EVC evidence, but it directly evaluates speaker similarity and emotion similarity in cross-speaker emotion transfer using sMOS, eMOS, SECS, and EECS (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). Its full system reports cross-speaker nMOS 4.23, sMOS 3.96, eMOS 4.07, SECS 0.8505, and EECS 0.4527 in the ablation table (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

[[hierarchical-emotion-rendering]] is TTS-adjacent evidence that speaker similarity can be reported alongside fine-grained emotion-control metrics, but it should not be treated as EVC speaker-preservation evidence because it does not convert source speech into target emotional speech (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Gap

The wiki does not yet contain a study that directly sweeps target emotion intensity or conversion strength and measures speaker similarity at each point. Current papers mostly compare systems, endpoints, or ablations rather than a controlled speaker-emotion frontier (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf; source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf; source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf). A claim such as "stronger emotion causes speaker drift" should be marked as needing verification until a controlled frontier experiment is available.

## Related pages

- [[speaker-emotion-tradeoff]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emo-stargan]]
- [[durflex-evc]]
- [[pflow-vc]]
- [[emoconv-diff]]
- [[starganv2-vc]]
- [[time-varying-timbre-tokens]]
- [[adversarial-source-classifier-loss]]
- [[clapfm-evc]]
- [[diemo-tts]]
- [[cross-speaker-emotion-transfer]]
- [[speaker-similarity-metrics]]
- [[hierarchical-emotion-rendering]]
- [[prabhu-2023-in-the-wild-sec]]
- [[einet]]
- [[ssl-disentanglement-for-sec]]
- [[vad-based-emotion-intensity]]
