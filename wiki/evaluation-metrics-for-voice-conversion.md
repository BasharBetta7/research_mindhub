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
- Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf
- Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf
- Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf
- Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf
- Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf
- Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf
- Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf
- Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf
- Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf
- Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf
- Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf
- Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf
- Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf
- Didi+et+al.pdf

**Last updated**: 2026-05-06

---

## Subjective metrics

The paper uses MOS ratings from online subjects to assess naturalness on a 1 to 5 scale (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). It also asks subjects to rate whether pairs of audio clips could have come from the same speaker, disregarding distortion, speed, and tone (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Objective metrics

The paper uses MOSNet predicted MOS as an objective proxy for naturalness, AlexNet speaker classification accuracy as a speaker similarity proxy, and ASR character error rate as an intelligibility proxy (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

For emotion-preserving anonymisation, Emo-StarGAN evaluates emotion preservation with Accorig, Accsvm, emotion embedding MAE, and pitch correlation coefficient; it evaluates voice quality with pMOS, intelligibility with CER, and anonymisation with EER (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

The [[speaker-emotion-tradeoff]] can be measured by comparing speaker/anonymisation metrics such as EER against emotion metrics such as Accorig, Accsvm, embedding MAE, and PCC (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

[[speaker-identity-evaluation-in-evc]] separates the speaker-side metrics used in the wiki from emotion-side metrics, because different papers use different notions of "speaker identity": anonymisation EER in Emo-StarGAN, speaker classification accuracy in StarGANv2-VC, subjective sMOS and objective SECS in DurFlex-EVC, and SECS/SMOS in PFlow-VC (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

[[speaker-similarity-metrics]] groups those speaker-side measures so they are not treated as interchangeable: EER measures anonymisation, speaker classification accuracy measures target-speaker recognizability under a classifier, and sMOS/SMOS/SECS measure perceived or embedding-based speaker similarity (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf; source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

For sequence-to-sequence emotional voice conversion, Emovox uses MCD for spectral distortion and DDUR for duration distortion, because duration conversion is part of the model's output behavior (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). It also uses MOS for emotion similarity and best-worst scaling to evaluate speech quality, emotion intensity, and emotion similarity (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

[[yang-2022-seq2seq-evc-overview]] lists the broader Seq2Seq EVC metric set as WER, CER, cosine similarity, MCD, DDUR, VDE, GPE, FFE, subjective speech emotion recognition, MOS, ABX, and best-worst scaling (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). This matters because Seq2Seq EVC changes more than spectral frames: evaluation may need to check content, duration, pitch, emotion, and subjective similarity together (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

For CycleGAN-based emotional voice conversion, Zhou et al. 2020 evaluates spectrum conversion with MCD and F0 conversion with RMSE and PCC, then uses XAB listening tests for emotion similarity (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

For [[emovoice]], emotional TTS evaluation uses WER for content consistency, emotion2vec-based emotion similarity, emotion2vec classification recall, UTMOS for perceptual quality, and human MOS for emotional expressiveness and instruction following (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). Although this is a TTS setup, the metric caution is relevant to emotional VC because it tests whether automatic emotion metrics align with human judgments (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

For [[emoconv-diff]], non-parallel in-the-wild evaluation uses SER prediction errors against target arousal and DNSMOS for non-intrusive speech quality, because paired target references are unavailable (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This is a different evaluation regime from MCD or paired-reference metrics because [[in-the-wild-emotion-conversion]] lacks ground-truth target utterances (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

For [[emomix]], emotional TTS evaluation uses MOS, SMOS, MCD, CMOS, CSMOS, and SER classifier probabilities for mixed-emotion analysis (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). The SER-probability analysis is useful as a diagnostic but should not be treated as equivalent to human perception of mixed emotions (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

For [[deepest]], evaluation uses MCD, MOS, AB preference for speech quality, and XAB preference for emotion similarity (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). For [[durflex-evc]], evaluation combines subjective nMOS, sMOS, and eMOC with objective UTMOS, PER, CER, WER, ECA, EECS, SECS, RTF, and prosody RMSE/DDUR metrics (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

For [[pflow-vc]], zero-shot VC evaluation uses WER, speaker embedding cosine similarity, QMOS, SMOS, and RTF, while emotion style transfer uses an emotion2vec-derived emotion consistency score (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

For [[clapfm-evc]], reference-speech and prompt-driven EVC evaluation uses MCD, RMSE, CER, UTMOS, nMOS, EECS, and eMOS (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). The absence of an explicit speaker-similarity metric in the main reported comparison is important when using ClapFM-EVC as evidence for speaker preservation (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

For [[diemo-tts]], cross-speaker emotion transfer evaluation uses nMOS, sMOS, eMOS, WER, CER, SECS, and EECS (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf). This metric set is especially relevant to the speaker-emotion tradeoff, but it belongs to TTS rather than EVC (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

For [[daisy-tts]], evaluation uses MOS for speech naturalness and a human emotion perception test for emotion perceivability (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). The paper also reports that increasing emotion intensity tends to improve emotion perceivability, although this is TTS evidence rather than EVC evidence (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

For [[emodiff]], emotional TTS evaluation uses MOS, MCD, classifier probability under intensity sweeps, and diversity preference tests (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). Its classifier-probability intensity metric is useful for controlled-sampling diagnostics, but it remains a proxy rather than a human perceptual measure (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

For [[hierarchical-emotion-rendering]], emotional TTS evaluation includes WER, MCD, pitch distortion, energy distortion, speaker embedding cosine similarity, emotion-controllability correlations, MUSHRA naturalness, MUSHRA emotional similarity, and best-worst scaling for utterance- and word-level controllability (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf). This is a useful TTS-side example of evaluating emotion control and speaker similarity together, but it is not a voice-conversion tradeoff experiment (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

For [[e3-tts]], general TTS evaluation uses MOS on a proprietary single-speaker dataset, SQuId and speaker similarity for prompt TTS and text editing, and a speaker-identification task based on diffusion timestep sampling (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf). These metrics are relevant to TTS backbone evaluation but not to emotion conversion (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

For [[glow-tts]], general TTS evaluation uses MOS, synthesis speed, long-utterance robustness, and multi-speaker MOS; the paper also includes a voice-conversion-style speaker-inversion experiment (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf). These results are architectural background and should not be used as evidence for EVC emotion preservation (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

For [[tf-mamba-ser]], SER evaluation uses weighted accuracy and unweighted accuracy on IEMOCAP and weighted F1 on MELD (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf). This is relevant because emotional speech generation papers often use SER predictions or embeddings as objective emotion proxies, but TF-Mamba itself is not a voice-conversion evaluation study (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

For [[prabhu-2023-in-the-wild-sec]], in-the-wild SEC evaluation uses SER mean-squared and mean-absolute arousal errors plus WVMOS for objective naturalness (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf). This metric set fits the non-parallel setting, but it does not directly measure converted-speaker similarity (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

For [[einet]], EVC evaluation uses MCD, log-F0 RMSE, DDUR, external SER classification accuracy, MOS naturalness, and subjective emotion similarity (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf). These metrics capture acoustic distortion, prosody, rhythm, emotion recognizability, and subjective quality, but the main reported table does not include a standard speaker-similarity metric (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

For [[diffevc]], any-to-any EVC evaluation uses UTMOS, DNSMOS, SECS, emotion conversion accuracy, emotion retrieval accuracy, MOS, neutral MOS, speaker MOS, and subjective emotion conversion accuracy (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). This metric set is important because it places speaker similarity and emotion conversion in the same table, making it more useful for tradeoff analysis than emotion-only evaluation (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

For [[zest]], zero-shot audio-to-audio emotion transfer evaluation uses CER for content preservation, emotion conversion accuracy for target-emotion transfer, speaker classification accuracy for source-speaker preservation, and subjective MOS, emotion-similarity MOS, and speaker-similarity MOS (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf). This is a clean three-axis setup for emotional voice conversion: content, emotion, and speaker identity are all checked separately (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

For [[textless-speech-emotion-conversion]], evaluation uses MOS for quality, emotion mean-opinion classification for perceived emotion, and ASR WER/PER for lexical preservation (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf). The paper's decomposition ablation is also an evaluation caution, because changing only the emotion label performs poorly compared with changing F0, duration, and translated units (source: Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf).

For [[zhou-2022-evc-theory-esd]], the ESD reference EVC experiments use MCD for objective spectral distortion, MOS for speech quality, and XAB preference for emotion similarity (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). The MOS instruction includes linguistic information and speaker identity preservation as part of speech quality, but the paper does not report a separate speaker-similarity metric in those reference experiments (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

For [[sgevc]], evaluation uses emotion classification accuracy for the latent emotion variable, MOS naturalness, emotion-similarity MOS, and MCD (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). This records emotion control and speech quality well, but it leaves speaker preservation under-measured because no dedicated speaker similarity score is reported (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

For [[seq2seq-cyclegan-evc]], evaluation uses MCD, F0 RMSE, SSIM, x-vector speaker similarity, naturalness MOS, and emotional-similarity MOS (source: Didi+et+al.pdf). This is a stronger metric set for the [[speaker-emotion-tradeoff]] than emotion-only evaluation, but the source also conflicts with the canonical ESD metadata, so its dataset description and quantitative claims should be verified before being used as central evidence (source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

For [[voicebox]], general speech generation evaluation uses WER, audio-context similarity, Frechet Speech Distance, QMOS, and SMOS (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf). Voicebox's critique of signal-level metrics is relevant to speech generation evaluation because deterministic metrics can unfairly penalize valid diverse samples (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

For [[tacotron]], general TTS evaluation uses 5-scale MOS for naturalness and ablation analysis of attention alignment and post-processing behavior (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf). This is historical TTS evaluation context and not EVC evaluation evidence (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

## Reported values

Full [[starganv2-vc]] reports pMOS 3.95, speaker classification accuracy 96.20%, and CER 12.55% (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). AUTO-VC reports pMOS 3.43, speaker classification accuracy 50.30%, and CER 47.43% in the same objective comparison table (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Caution

The authors note that pMOS, speaker classification accuracy, and CER are not sensitive to F0, because removing [[f0-consistency-loss]] does not reduce those metrics even though converted samples can have unnatural intonation (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). This is an important limitation when using objective metrics alone for emotional or expressive speech conversion (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

Emo-StarGAN's surprise results show another metric caution: the method improves aggregate emotion scores but still reports low Accorig for surprise, so aggregate emotion-preservation metrics can hide emotion-specific failures (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

For intensity-control experiments, the Emovox paper is a warning that intensity claims should be checked across multiple prosodic cues, because the authors show different emotion types can express stronger intensity through different cues such as pitch, energy, or duration (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

The 2020 CycleGAN/CWT paper gives a related warning: objective spectral metrics alone do not capture prosody conversion quality, so F0-specific metrics and listening tests are needed when evaluating emotional voice conversion (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

The EmoVoice paper adds a stronger warning for fine-grained emotion evaluation: emotion2vec similarity has high system-level Spearman correlation with human ratings but only 0.4047 sentence-level Spearman correlation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). GPT-4o-audio and Gemini ratings also show weak sentence-level correlations of 0.2569 and 0.1960, so multimodal LLM judging is not yet reliable as a replacement for human sample-level evaluation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

[[emotion2vec]] should therefore be treated as a useful proxy for system comparison, not a substitute for human sentence-level perceptual evaluation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

EmoConv-Diff adds a practical caution for in-the-wild work: when no parallel reference exists, intrusive metrics cannot be used, so evaluation shifts toward proxy SER errors and non-intrusive quality metrics (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This makes human listening tests especially important for claims about speaker preservation and perceived target emotion quality.

The DeepEST and PFlow-VC papers add another recurring caution: SER or emotion2vec can serve as conditioning or evaluation machinery, but then the system may be optimized and judged through the same kind of proxy representation (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). DurFlex-EVC partly reduces this risk by reporting both subjective and objective emotion/speaker metrics, but it still uses acted ESD rather than in-the-wild data (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

Yang et al. 2022 gives a survey-level version of the same caution: objective metrics only indicate closeness under a chosen measurement and do not guarantee that humans perceive the converted speech as close to the target (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf). The paper argues that subjective annotations remain the gold standard for EVC evaluation until automatic perceptual evaluation matures (source: Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf).

ClapFM-EVC adds a new caution for prompt-controlled EVC: a system can report strong emotion similarity and naturalness while still leaving speaker preservation under-measured if speaker-side metrics are absent from the main evaluation (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

The new emotional TTS sources strengthen a broader caution: speaker metrics can appear in TTS papers, but they do not automatically answer whether EVC emotion conversion causes speaker drift (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf; source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf; source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

[[tf-mamba-ser]] strengthens the SER-proxy side of evaluation, but it does not remove the gap between automatic recognition and human-perceived emotional quality (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf). If a future EVC system reports TF-Mamba-based emotion accuracy, it should still be paired with listening tests and speaker-side metrics (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The newest direct EVC intensity sources sharpen the same warning: [[prabhu-2023-in-the-wild-sec]] and [[einet]] evaluate controllable emotion conversion, but neither reports a full speaker-similarity sweep over emotion intensity (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf; source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

[[diffevc]] partially addresses this gap by reporting SECS and emotion accuracy under expressive guidance, but a guidance-scale curve would still be needed to claim a measured intensity-speaker frontier (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). [[zest]] similarly evaluates speaker preservation and emotion transfer together, but its settings compare tasks and ablations rather than continuously sweeping emotion strength (source: Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf).

The new semi-supervised and hybrid sources sharpen the same caution: [[sgevc]] has explicit speaker and emotion variables but lacks a speaker metric, while [[seq2seq-cyclegan-evc]] has a speaker metric but contains a dataset-metadata contradiction (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf; source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

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
- [[yang-2022-seq2seq-evc-overview]]
- [[clapfm-evc]]
- [[diemo-tts]]
- [[daisy-tts]]
- [[natural-language-emotion-control]]
- [[emotion2vec]]
- [[speaker-similarity-metrics]]
- [[emodiff]]
- [[soft-label-guidance]]
- [[hierarchical-emotion-rendering]]
- [[hierarchical-emotion-control]]
- [[e3-tts]]
- [[glow-tts]]
- [[tf-mamba-ser]]
- [[temporal-frequency-ser]]
- [[prabhu-2023-in-the-wild-sec]]
- [[einet]]
- [[vad-based-emotion-intensity]]
- [[voicebox]]
- [[text-guided-speech-infilling]]
- [[tacotron]]
- [[seq2seq-tts]]
- [[diffevc]]
- [[expressive-guidance]]
- [[zest]]
- [[zero-shot-audio-to-audio-emotion-transfer]]
- [[textless-speech-emotion-conversion]]
- [[textless-emotion-conversion]]
- [[zhou-2022-evc-theory-esd]]
- [[esd-dataset]]
- [[sgevc]]
- [[semi-supervised-evc]]
- [[seq2seq-cyclegan-evc]]
