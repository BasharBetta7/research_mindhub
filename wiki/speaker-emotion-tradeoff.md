# Speaker Emotion Tradeoff

**Summary**: The current wiki suggests that speaker conversion or anonymisation can conflict with emotion preservation, but the strongest available evidence shows Emo-StarGAN improves emotion preservation without measurable loss in anonymisation EER. Several papers measure speaker identity and emotion together, but a systematic speaker-emotion Pareto frontier is not yet documented.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf
- Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf
- Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf
- Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf
- Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf
- Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf
- Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Definition

The speaker-emotion tradeoff refers to the possibility that changing or hiding speaker identity may damage the emotional content of speech, or that preserving emotion may reduce speaker conversion or anonymisation effectiveness (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). In [[emotion-preserving-voice-conversion]], this tradeoff is central because the goal is to modify speaker timbre while preserving linguistic and emotional content (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Evidence from Emo-StarGAN

The clearest evidence comes from [[emo-stargan]], which reports large emotion-preservation gains while keeping anonymisation almost unchanged (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). Across all conversions, Emo-StarGAN improves Accorig from 20.2% to 72.4%, Accsvm from 39.4% to 87.1%, embedding MAE from 48.9 to 40.8, and PCC from 78.9 to 84.3, while EER remains essentially unchanged at 49.63 versus 49.64 (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

This suggests that, in the Emo-StarGAN aggregate evaluation, improving emotion preservation does not measurably weaken speaker anonymisation (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). However, this is not the same as a full Pareto frontier, because the paper does not sweep a control variable across speaker and emotion objectives to trace tradeoff points (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Evidence from StarGANv2-VC

[[starganv2-vc]] appears to favor speaker conversion/anonymisation more than emotion preservation when used directly for anonymisation, because Emo-StarGAN is motivated by the claim that vanilla StarGANv2-VC achieves anonymisation but fails to preserve emotion (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

The [[adversarial-source-classifier-loss]] ablation shows that speaker identity control can change substantially while naturalness and intelligibility metrics remain similar: removing the loss reduces speaker classification accuracy from 96.20% to 63.90%, while pMOS remains similar at 3.98 and CER remains similar at 12.33% (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). This evidence is speaker-focused rather than emotion-focused, but it shows that speaker identity metrics can move independently from other quality metrics (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Measurable trends

The current wiki supports four measurable trends:

1. Emotion preservation can improve strongly without an aggregate EER penalty in Emo-StarGAN (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

2. Emotion-aware losses may trade off with intelligibility rather than anonymisation; for example, adding only spectral-kurtosis acoustic feature loss improves Accorig from 20.2% to 30.1% and PCC from 78.9 to 80.4, but worsens CER from 3.42% to 5.52% (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

3. Aggregate emotion metrics can hide per-emotion failures; Emo-StarGAN reports weak surprise preservation, with surprise Accorig of 16.0% for ESD to ESD and 0.0% for RAVDESS to ESD (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

4. Later systems increasingly report speaker identity and emotion metrics together, such as DurFlex-EVC with sMOS, SECS, eMOC, ECA, and EECS, and PFlow-VC with SECS and emotion consistency score (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). This is stronger than reporting emotion alone, but it is still not a controlled tradeoff curve.

## Speaker identity evaluation

[[speaker-identity-evaluation-in-evc]] collects the relevant speaker-side measurements across the wiki, including anonymisation EER, speaker classification accuracy, sMOS, SECS, and speaker-similarity MOS (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). The existence of these metrics means speaker identity is being measured in EVC-adjacent studies, but the current wiki audit found no controlled study of the causal effect of stronger emotion conversion on speaker identity.

## Open gap

The wiki does not yet document a systematic speaker-emotion tradeoff curve, alpha sweep, or Pareto frontier that jointly measures speaker similarity or anonymisation against emotion preservation (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). Any claim about a smooth speaker-emotion frontier should be marked as needing verification until supported by an experiment or source.

[[emovoice]] reinforces the evaluation side of this gap, because it shows that automatic emotion metrics and multimodal LLM judges can have weak sentence-level alignment with human perception (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). However, EmoVoice is TTS rather than VC, so it should not be cited as evidence that speaker drift increases or decreases under stronger emotion generation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

[[emoconv-diff]] is relevant because it explicitly aims to preserve speaker identity while converting arousal on in-the-wild speech (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). However, the reported evaluation emphasizes SER arousal error and DNSMOS rather than a full speaker-emotion Pareto curve, so it does not close the tradeoff gap by itself (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

[[emomix]] should not be used as evidence for this tradeoff because it is emotional TTS, not voice conversion (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). Its diffusion mixing idea could inspire future VC experiments, but speaker preservation would need to be tested separately.

[[durflex-evc]] is relevant because it reports both speaker similarity and emotion metrics while improving duration/prosody modelling, but it does not sweep an explicit emotion-strength or speaker-preservation control variable (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). [[pflow-vc]] is valuable adjacent evidence because it improves zero-shot speaker similarity and emotion consistency with pitch and timbre tokens, but its emotion metric is emotion2vec-based and the paper is expressive VC rather than dedicated EVC (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

[[yang-2022-seq2seq-evc-overview]] states the standard EVC goal of changing the emotional state while preserving linguistic information and speaker identity (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). This supports the conceptual importance of the [[speaker-emotion-tradeoff]], but it is not direct evidence for speaker drift because the survey does not measure speaker similarity as emotion conversion strength changes (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

[[clapfm-evc]] is directly relevant because it supports prompt-based or reference-based EVC with adjustable emotion intensity (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). However, its main reported comparison uses quality and emotion-similarity metrics rather than explicit speaker-similarity metrics, so it still does not establish a speaker-emotion frontier (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

[[diemo-tts]] is adjacent but analytically useful because it directly names the difficulty of separating speaker identity from emotion-related prosody in cross-speaker emotion transfer (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). It reports both speaker and emotion metrics, but it is TTS rather than EVC and therefore should not be cited as direct EVC speaker-drift evidence (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

[[daisy-tts]] is relevant to intensity and mixed-emotion control, but it should not be used as speaker-emotion tradeoff evidence because it is emotional TTS and does not measure speaker identity drift (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

[[emodiff]] is relevant to intensity control because it sweeps target emotion strength through soft-label guidance, but it should not be used as speaker-emotion tradeoff evidence because the task is single-speaker emotional TTS rather than EVC (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

[[hierarchical-emotion-rendering]] reports speaker-similarity metrics alongside hierarchical emotion-control metrics, but it still does not establish the EVC speaker-emotion tradeoff because it synthesizes speech from text rather than converting a source speaker to a target emotional speech sample (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf). Its useful contribution to this page is methodological: future EVC tradeoff studies may need speaker metrics at the same time as utterance-, word-, and phoneme-level emotion-control metrics (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

[[tf-mamba-ser]] is relevant only on the measurement side: a stronger SER model could provide a better automatic emotion proxy for tradeoff experiments, but it does not itself test whether emotion conversion changes speaker identity (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

[[prabhu-2023-in-the-wild-sec]] is direct in-the-wild SEC evidence because it designs separate SSL representations for lexical content, speaker identity, and arousal (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf). It still does not close the tradeoff gap because the reported evaluation focuses on SER arousal errors and WVMOS rather than explicit speaker similarity after conversion (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

[[einet]] is direct EVC evidence for controllable emotional intensity and explicitly adds an identity maintainer to reduce speaker identity loss under intensity manipulation (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf). However, it reports naturalness, emotion similarity, F0, duration, and SER accuracy rather than a standard speaker-similarity metric, so it still does not provide a speaker-emotion Pareto frontier (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

[[voicebox]] and [[tacotron]] should not be used as speaker-emotion tradeoff evidence because they are general speech generation or TTS backbone papers rather than EVC studies (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf; source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf). Voicebox is especially tempting to overcite because it transfers audio style from context, but the paper explicitly states that it cannot independently control voice, speaking style, emotion, and acoustic condition (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Related pages

- [[emo-stargan]]
- [[emotion-preserving-voice-conversion]]
- [[speech-anonymisation]]
- [[speaker-disentanglement]]
- [[adversarial-source-classifier-loss]]
- [[emotion-aware-acoustic-feature-loss]]
- [[emotion-embedding-loss]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emovoice]]
- [[synthetic-emotional-speech-data]]
- [[emoconv-diff]]
- [[in-the-wild-emotion-conversion]]
- [[arousal-based-emotion-control]]
- [[durflex-evc]]
- [[pflow-vc]]
- [[time-varying-timbre-tokens]]
- [[pitch-conditioned-flow-matching]]
- [[speaker-identity-evaluation-in-evc]]
- [[yang-2022-seq2seq-evc-overview]]
- [[clapfm-evc]]
- [[diemo-tts]]
- [[daisy-tts]]
- [[cross-speaker-emotion-transfer]]
- [[adaptive-intensity-gate]]
- [[speaker-similarity-metrics]]
- [[self-supervised-emotion-disentanglement]]
- [[emodiff]]
- [[soft-label-guidance]]
- [[hierarchical-emotion-rendering]]
- [[hierarchical-emotion-control]]
- [[tf-mamba-ser]]
- [[temporal-frequency-ser]]
- [[prabhu-2023-in-the-wild-sec]]
- [[ssl-disentanglement-for-sec]]
- [[einet]]
- [[vad-based-emotion-intensity]]
- [[voicebox]]
- [[tacotron]]
