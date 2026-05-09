# Wiki Index

**Summary**: Table of contents for the speech emotion generation research wiki.

**Sources**: Personal wiki metadata.

**Last updated**: 2026-05-08

---

## Source summaries

- [sources.bib](../sources.bib) - BibTeX bibliography for the source files stored in `research_mindhub/raw/`.
- [[autovc]] - Summary of Qian et al. 2019, the AutoVC paper for non-parallel many-to-many and zero-shot voice conversion with only autoencoder loss.
- [[clapfm-evc]] - Summary of Pan et al. 2025, the prompt- and reference-controlled emotional voice conversion paper.
- [[daisy-tts]] - Summary of Chevi and Aji 2024, the emotional TTS paper using prosody embedding decomposition.
- [[diemo-tts]] - Summary of Cho et al. 2025, the cross-speaker emotional TTS paper using self-supervised emotion disentanglement.
- [[diffevc]] - Summary of Chou et al. 2024, the any-to-any diffusion EVC paper using expressive guidance and mutual-information disentanglement.
- [[e3-tts]] - Summary of Gao et al. 2023, the end-to-end diffusion TTS paper that directly generates waveform from text.
- [[emo-stargan]] - Summary of Ghosh et al. 2023, the Emo-StarGAN paper for semi-supervised emotion-preserving voice conversion.
- [[emoconv-diff]] - Summary of Prabhu et al. 2024, the EmoConv-Diff paper for diffusion-based speech emotion conversion on non-parallel in-the-wild data.
- [[emodiff]] - Summary of Guo et al. 2023, the emotional TTS paper using soft-label guidance for intensity control.
- [[emomix]] - Summary of Tang et al. 2023, the EmoMix paper for diffusion-based emotional TTS with mixed emotion synthesis.
- [[emotion-intensity-and-control]] - Summary of Zhou et al. 2023, the Emovox paper for emotion intensity modelling and control in emotional voice conversion.
- [[emovoice]] - Summary of Yang et al. 2025, the EmoVoice paper for LLM-based emotional TTS with freestyle text prompting.
- [[glow-tts]] - Summary of Kim et al. 2020, the flow-based TTS paper introducing Monotonic Alignment Search.
- [[hierarchical-emotion-rendering]] - Summary of Inoue et al. 2025, the emotional TTS paper for utterance-, word-, and phoneme-level emotion rendering control.
- [[deepest]] - Summary of Zhou et al. 2021, the DeepEST paper for seen and unseen emotional style transfer and the ESD dataset.
- [[durflex-evc]] - Summary of Oh et al. 2025, the DurFlex-EVC paper for duration-flexible EVC without text alignment.
- [[einet]] - Summary of Qi et al. 2024, the Emotional Intensity-aware Network for controllable realistic EVC.
- [[pflow-vc]] - Summary of Zuo et al. 2025, the PFlow-VC paper for expressive VC with pitch-conditioned flow matching.
- [[prabhu-2023-in-the-wild-sec]] - Summary of Prabhu et al. 2023, the SSL-disentangled in-the-wild speech emotion conversion paper.
- [[promptevc]] - Summary of Qi et al. 2025, the prompt-controlled emotional voice conversion paper using natural-language emotion descriptions.
- [[seq2seq-cyclegan-evc]] - Summary of Didi et al. 2025, the hybrid Seq2Seq and CycleGAN EVC paper, with an ESD metadata caution.
- [[sgevc]] - Summary of Zhu et al. 2023, the semi-supervised generative EVC paper using explicit speaker and emotion variables.
- [[starganv2-vc]] - Summary of Li et al. 2021, the StarGANv2-VC paper for unsupervised non-parallel many-to-many voice conversion.
- [[tacotron]] - Summary of Wang et al. 2017, the end-to-end sequence-to-sequence TTS paper.
- [[tf-mamba-ser]] - Summary of Zhao et al. 2024, the temporal-frequency Mamba paper for efficient speech emotion recognition.
- [[textless-speech-emotion-conversion]] - Summary of Kreuk et al. 2022, the textless SEC paper using discrete speech-unit translation and decomposed prosody.
- [[transforming-spectrum-and-prosody-for-evc]] - Summary of Zhou et al. 2020, the CycleGAN/CWT paper for non-parallel spectrum and prosody conversion in EVC.
- [[voicebox]] - Summary of Le et al. 2023, the large-scale text-guided speech infilling and flow-matching speech generation paper.
- [[yang-2022-seq2seq-evc-overview]] - Summary of Yang et al. 2022, the survey of sequence-to-sequence emotional voice conversion.
- [[zhou-2022-evc-theory-esd]] - Summary of Zhou et al. 2022, the EVC survey and canonical ESD dataset paper.
- [[zest]] - Summary of Dutta and Ganapathy 2024, the zero-shot audio-to-audio emotion transfer paper with speaker disentanglement.

## Concepts

- [[adversarial-source-classifier-loss]] - Loss introduced by StarGANv2-VC to improve target speaker identity in converted speech.
- [[asr-speech-consistency-loss]] - ASR-feature loss used to preserve linguistic content during conversion.
- [[arousal-based-emotion-control]] - Continuous arousal-based control of emotional activation or intensity.
- [[autoencoder-voice-conversion]] - Encoder-decoder voice conversion that separates content from speaker/style information.
- [[adaptive-intensity-gate]] - ClapFM-EVC module for scaling emotional features to adjust conversion intensity.
- [[cross-speaker-emotion-transfer]] - Transfer of reference emotion to another target speaker while preserving target timbre.
- [[cyclegan-evc]] - CycleGAN-based emotional voice conversion with non-parallel emotion-domain training.
- [[cwt-f0-modelling]] - Multi-scale F0 representation using continuous wavelet transform.
- [[diffusion-based-emotion-conversion]] - Diffusion-model approach to emotional speech conversion and related emotional speech generation.
- [[diffusion-emotion-mixing]] - Runtime mixing of diffusion denoising predictions from multiple emotion conditions.
- [[deep-emotional-features]] - SER-derived continuous emotion descriptors used for emotional style transfer.
- [[discrete-speech-units-for-evc]] - Learned speech units used for alignment-free emotional voice conversion.
- [[duration-flexible-evc]] - EVC that explicitly models duration and rhythm as part of emotion conversion.
- [[end-to-end-diffusion-tts]] - Diffusion TTS that directly generates waveform from text without an intermediate acoustic representation.
- [[emotion-aware-acoustic-feature-loss]] - Emo-StarGAN loss comparing source and converted emotion-correlated acoustic descriptors.
- [[emotion-classifier-loss]] - Direct emotion supervision loss used by Emo-StarGAN when labels are available.
- [[emotion-embedding-loss]] - Emo-StarGAN loss comparing latent emotion representations of source and converted speech.
- [[emotion-intensity-control]] - Fine-grained control of how strongly a target emotion is expressed.
- [[emotion2vec]] - Self-supervised speech emotion representation used as an emotion-similarity proxy.
- [[emotion-preserving-voice-conversion]] - Speaker conversion that preserves the source utterance's emotion.
- [[emotional-speech-databases]] - Emotional speech corpora used to train and evaluate EVC and emotional speech generation systems.
- [[end-to-end-generative-evc]] - Generative EVC that integrates conversion and waveform synthesis in one model family.
- [[esd-dataset]] - Bilingual parallel emotional speech dataset central to many EVC benchmarks.
- [[expressive-guidance]] - DiffEVC inference-time guidance for strengthening target emotion while controlling speaker/emotion conditions.
- [[evc-clap]] - Contrastive language-audio pretraining module for prompt-controlled emotional voice conversion.
- [[emovoice-db]] - Synthetic English emotional speech dataset with natural-language emotion descriptions.
- [[emotional-speech-conversion]] - Conversion of speech toward emotional styles while preserving content.
- [[emovox]] - Sequence-to-sequence emotional voice conversion framework with emotion intensity control.
- [[evaluation-metrics-for-voice-conversion]] - Subjective and objective metrics used for naturalness, speaker similarity, and intelligibility.
- [[f0-pitch-contour-in-voice-conversion]] - Why pitch contour extraction is used in VC and EVC, including naturalness, emotion intensity, and speaker-identity caveats.
- [[f0-consistency-loss]] - Pitch-contour preservation loss based on normalized F0.
- [[flow-based-tts]] - TTS with generative normalizing flows, currently represented by Glow-TTS.
- [[flow-matching-evc]] - Emotional or expressive voice conversion using conditional flow matching decoders.
- [[freestyle-emotion-prompting]] - Speech emotion control using natural-language affect descriptions rather than fixed class labels.
- [[information-bottleneck-for-voice-conversion]] - AutoVC bottleneck mechanism for balancing reconstruction and speaker disentanglement.
- [[in-the-wild-emotion-conversion]] - Emotional speech conversion on naturalistic non-parallel recordings with real-world variability.
- [[hierarchical-emotion-control]] - Fine-grained emotion control at utterance, word, and phoneme levels.
- [[hierarchical-emotion-distribution]] - Soft emotion-intensity distributions extracted at multiple segment levels for hierarchical emotion control.
- [[llm-based-emotional-tts]] - Emotional TTS approach that uses an LLM backbone to interpret text and emotion instructions.
- [[many-to-many-voice-conversion]] - Voice conversion among multiple source and target speaker domains.
- [[mapping-network]] - Latent-to-style module used for diverse target-domain style sampling.
- [[mixed-emotion-synthesis]] - Speech synthesis that expresses combinations of multiple emotional qualities.
- [[monotonic-alignment-search]] - Dynamic-programming alignment mechanism used by Glow-TTS.
- [[mutual-information-disentanglement]] - Reducing statistical dependence between speaker and emotion representations.
- [[natural-language-emotion-control]] - Prompt-based control of target emotional expression in TTS or EVC.
- [[non-parallel-voice-conversion]] - Voice conversion trained without paired source-target utterances.
- [[objective-speech-evaluation-metrics]] - Glossary of objective and semi-objective speech metrics used for quality, content, speaker, emotion, and prosody evaluation.
- [[parallel-emotional-speech-data]] - Matched emotional utterance data used by Seq2Seq EVC and limited by scarcity and collection cost.
- [[relative-attributes-for-emotion-intensity]] - Ranking-based representation for emotion intensity without explicit intensity labels.
- [[sequence-to-sequence-emotional-voice-conversion]] - EVC approach that jointly models acoustic conversion and duration alignment.
- [[ser-perceptual-loss]] - Emotion supervision from a pretrained speech emotion recognizer.
- [[self-supervised-emotion-disentanglement]] - Teacher-student emotion representation learning that reduces speaker leakage.
- [[separate-vs-joint-prosody-training]] - Comparison of separate and joint learning for spectrum and prosody conversion.
- [[seq2seq-tts]] - Sequence-to-sequence text-to-speech with attention-based acoustic-frame generation.
- [[semi-supervised-evc]] - EVC with limited emotion labels and unlabeled or weakly labeled emotional speech.
- [[seq2seq-cyclegan-refinement]] - Two-stage EVC pattern combining Seq2Seq temporal modelling with CycleGAN spectral refinement.
- [[soft-label-guidance]] - Diffusion classifier-guidance variant that controls emotion intensity with weighted emotion labels.
- [[speaker-emotion-tradeoff]] - Evidence and open gaps around speaker conversion/anonymisation versus emotion preservation.
- [[speaker-disentanglement]] - Removing speaker identity from content representations while preserving conversion-relevant information.
- [[speaker-similarity-metrics]] - Speaker-side metrics such as EER, speaker classification accuracy, sMOS, SMOS, and SECS.
- [[ssl-disentanglement-for-sec]] - Self-supervised disentanglement of lexical, speaker, and emotion factors for speech emotion conversion.
- [[spectrum-prosody-conversion]] - Joint research concern of transforming spectral and prosodic emotion cues.
- [[source-reliability-notes]] - Central cautions for sources with metadata contradictions, task mismatch, proxy-metric limitations, or synthetic-data caveats.
- [[speech-anonymisation]] - Modifying speech to remove speaker identity while preserving content.
- [[speaker-identity-evaluation-in-evc]] - Metrics and evidence for speaker preservation, similarity, or anonymisation in emotional voice conversion.
- [[stargan-v2]] - Multi-domain style transfer GAN adapted by StarGANv2-VC.
- [[style-pretraining-for-evc]] - Pretraining strategy using neutral multi-speaker speech before limited-data emotion training.
- [[style-encoder]] - Reference-based style extraction module.
- [[voice-conversion]] - General concept of changing voice identity or style while preserving linguistic content.
- [[phoneme-boosted-tts]] - TTS design that predicts phoneme tokens as auxiliary guidance for audio-token generation.
- [[pitch-conditioned-flow-matching]] - Flow matching VC conditioned on discrete pitch tokens for expressive prosody transfer.
- [[prosody-embedding-decomposition]] - Prosody latent-space manipulation for primary emotions, mixed emotions, intensity, and polarity.
- [[seen-and-unseen-emotion-transfer]] - Reference-conditioned transfer to emotion styles seen or unseen during conversion-model training.
- [[synthetic-emotional-speech-data]] - Emotional speech data generated by a model rather than recorded from human speakers.
- [[temporal-frequency-ser]] - Speech emotion recognition that models both temporal dynamics and frequency-domain structure.
- [[textless-emotion-conversion]] - Emotion conversion from learned speech units without requiring transcripts at conversion time.
- [[text-guided-speech-infilling]] - Speech generation task that fills masked speech from surrounding audio and transcript context.
- [[time-varying-timbre-tokens]] - Dynamic timbre representations used alongside global speaker embeddings.
- [[vad-based-emotion-intensity]] - Emotion intensity modeling with valence, arousal, and dominance values.
- [[zero-shot-voice-conversion]] - Voice conversion involving speakers unseen during conversion-model training.
- [[zero-shot-audio-to-audio-emotion-transfer]] - Reference-audio emotion transfer that preserves source speaker and content in zero-shot settings.

## Experiment critiques

- [Experiment wiki index](../exp_wiki/index.md) - Table of contents for analyses derived from `research_mindhub/exp/`.
- [Model inferred intensity alpha critique](../exp_wiki/model-inferred-intensity-alpha-critique.md) - Critique of the `MODEL_inferred_intensity` epoch and alpha sweeps, focused on emotion accuracy versus speaker drift.
- [Model inferred intensity gap analysis](../exp_wiki/model-inferred-intensity-gap-analysis.md) - Cross-condition critique of ESD SSST/DSST, CREMA-D runs, listening-study evidence, and missing analyses.
