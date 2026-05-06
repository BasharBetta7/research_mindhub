# Evaluation Metrics For Voice Conversion

**Summary**: StarGANv2-VC evaluates voice conversion using subjective MOS and similarity ratings, plus objective pMOS, speaker classification accuracy, and CER. The metrics separate naturalness, speaker identity, and intelligibility.

**Sources**:
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf

**Last updated**: 2026-05-06

---

## Subjective metrics

The paper uses MOS ratings from online subjects to assess naturalness on a 1 to 5 scale (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). It also asks subjects to rate whether pairs of audio clips could have come from the same speaker, disregarding distortion, speed, and tone (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Objective metrics

The paper uses MOSNet predicted MOS as an objective proxy for naturalness, AlexNet speaker classification accuracy as a speaker similarity proxy, and ASR character error rate as an intelligibility proxy (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

For emotion-preserving anonymisation, Emo-StarGAN evaluates emotion preservation with Accorig, Accsvm, emotion embedding MAE, and pitch correlation coefficient; it evaluates voice quality with pMOS, intelligibility with CER, and anonymisation with EER (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

The [[speaker-emotion-tradeoff]] can be measured by comparing speaker/anonymisation metrics such as EER against emotion metrics such as Accorig, Accsvm, embedding MAE, and PCC (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

[[speaker-identity-evaluation-in-evc]] separates the speaker-side metrics used in the wiki from emotion-side metrics, because different papers use different notions of "speaker identity": anonymisation EER in Emo-StarGAN, speaker classification accuracy in StarGANv2-VC, subjective sMOS and objective SECS in DurFlex-EVC, and SECS/SMOS in PFlow-VC (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

For sequence-to-sequence emotional voice conversion, Emovox uses MCD for spectral distortion and DDUR for duration distortion, because duration conversion is part of the model's output behavior (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). It also uses MOS for emotion similarity and best-worst scaling to evaluate speech quality, emotion intensity, and emotion similarity (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

For CycleGAN-based emotional voice conversion, Zhou et al. 2020 evaluates spectrum conversion with MCD and F0 conversion with RMSE and PCC, then uses XAB listening tests for emotion similarity (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

For [[emovoice]], emotional TTS evaluation uses WER for content consistency, emotion2vec-based emotion similarity, emotion2vec classification recall, UTMOS for perceptual quality, and human MOS for emotional expressiveness and instruction following (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). Although this is a TTS setup, the metric caution is relevant to emotional VC because it tests whether automatic emotion metrics align with human judgments (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

For [[emoconv-diff]], non-parallel in-the-wild evaluation uses SER prediction errors against target arousal and DNSMOS for non-intrusive speech quality, because paired target references are unavailable (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This is a different evaluation regime from MCD or paired-reference metrics because [[in-the-wild-emotion-conversion]] lacks ground-truth target utterances (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

For [[emomix]], emotional TTS evaluation uses MOS, SMOS, MCD, CMOS, CSMOS, and SER classifier probabilities for mixed-emotion analysis (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). The SER-probability analysis is useful as a diagnostic but should not be treated as equivalent to human perception of mixed emotions (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

For [[deepest]], evaluation uses MCD, MOS, AB preference for speech quality, and XAB preference for emotion similarity (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). For [[durflex-evc]], evaluation combines subjective nMOS, sMOS, and eMOC with objective UTMOS, PER, CER, WER, ECA, EECS, SECS, RTF, and prosody RMSE/DDUR metrics (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

For [[pflow-vc]], zero-shot VC evaluation uses WER, speaker embedding cosine similarity, QMOS, SMOS, and RTF, while emotion style transfer uses an emotion2vec-derived emotion consistency score (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Reported values

Full [[starganv2-vc]] reports pMOS 3.95, speaker classification accuracy 96.20%, and CER 12.55% (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). AUTO-VC reports pMOS 3.43, speaker classification accuracy 50.30%, and CER 47.43% in the same objective comparison table (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Caution

The authors note that pMOS, speaker classification accuracy, and CER are not sensitive to F0, because removing [[f0-consistency-loss]] does not reduce those metrics even though converted samples can have unnatural intonation (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). This is an important limitation when using objective metrics alone for emotional or expressive speech conversion (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

Emo-StarGAN's surprise results show another metric caution: the method improves aggregate emotion scores but still reports low Accorig for surprise, so aggregate emotion-preservation metrics can hide emotion-specific failures (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

For intensity-control experiments, the Emovox paper is a warning that intensity claims should be checked across multiple prosodic cues, because the authors show different emotion types can express stronger intensity through different cues such as pitch, energy, or duration (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

The 2020 CycleGAN/CWT paper gives a related warning: objective spectral metrics alone do not capture prosody conversion quality, so F0-specific metrics and listening tests are needed when evaluating emotional voice conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

The EmoVoice paper adds a stronger warning for fine-grained emotion evaluation: emotion2vec similarity has high system-level Spearman correlation with human ratings but only 0.4047 sentence-level Spearman correlation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). GPT-4o-audio and Gemini ratings also show weak sentence-level correlations of 0.2569 and 0.1960, so multimodal LLM judging is not yet reliable as a replacement for human sample-level evaluation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

EmoConv-Diff adds a practical caution for in-the-wild work: when no parallel reference exists, intrusive metrics cannot be used, so evaluation shifts toward proxy SER errors and non-intrusive quality metrics (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This makes human listening tests especially important for claims about speaker preservation and perceived target emotion quality.

The DeepEST and PFlow-VC papers add another recurring caution: SER or emotion2vec can serve as conditioning or evaluation machinery, but then the system may be optimized and judged through the same kind of proxy representation (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). DurFlex-EVC partly reduces this risk by reporting both subjective and objective emotion/speaker metrics, but it still uses acted ESD rather than in-the-wild data (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Related pages

- [[starganv2-vc]]
- [[adversarial-source-classifier-loss]]
- [[asr-speech-consistency-loss]]
- [[f0-consistency-loss]]
- [[emo-stargan]]
- [[emotion-preserving-voice-conversion]]
- [[emovox]]
- [[emotion-intensity-control]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[transforming-spectrum-and-prosody-for-evc]]
- [[cwt-f0-modelling]]
- [[speaker-emotion-tradeoff]]
- [[emovoice]]
- [[freestyle-emotion-prompting]]
- [[phoneme-boosted-tts]]
- [[emoconv-diff]]
- [[in-the-wild-emotion-conversion]]
- [[arousal-based-emotion-control]]
- [[emomix]]
- [[mixed-emotion-synthesis]]
- [[deepest]]
- [[durflex-evc]]
- [[pflow-vc]]
- [[deep-emotional-features]]
- [[duration-flexible-evc]]
- [[speaker-identity-evaluation-in-evc]]
