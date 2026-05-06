# Wiki Index

**Summary**: Table of contents for the speech emotion generation research wiki.

**Sources**: Personal wiki metadata.

**Last updated**: 2026-05-06

---

## Source summaries

- [[autovc]] - Summary of Qian et al. 2019, the AutoVC paper for non-parallel many-to-many and zero-shot voice conversion with only autoencoder loss.
- [[emo-stargan]] - Summary of Ghosh et al. 2023, the Emo-StarGAN paper for semi-supervised emotion-preserving voice conversion.
- [[emoconv-diff]] - Summary of Prabhu et al. 2024, the EmoConv-Diff paper for diffusion-based speech emotion conversion on non-parallel in-the-wild data.
- [[emomix]] - Summary of Tang et al. 2023, the EmoMix paper for diffusion-based emotional TTS with mixed emotion synthesis.
- [[emotion-intensity-and-control]] - Summary of Zhou et al. 2023, the Emovox paper for emotion intensity modelling and control in emotional voice conversion.
- [[emovoice]] - Summary of Yang et al. 2025, the EmoVoice paper for LLM-based emotional TTS with freestyle text prompting.
- [[deepest]] - Summary of Zhou et al. 2021, the DeepEST paper for seen and unseen emotional style transfer and the ESD dataset.
- [[durflex-evc]] - Summary of Oh et al. 2025, the DurFlex-EVC paper for duration-flexible EVC without text alignment.
- [[pflow-vc]] - Summary of Zuo et al. 2025, the PFlow-VC paper for expressive VC with pitch-conditioned flow matching.
- [[starganv2-vc]] - Summary of Li et al. 2021, the StarGANv2-VC paper for unsupervised non-parallel many-to-many voice conversion.
- [[transforming-spectrum-and-prosody-for-evc]] - Summary of Zhou et al. 2020, the CycleGAN/CWT paper for non-parallel spectrum and prosody conversion in EVC.

## Concepts

- [[adversarial-source-classifier-loss]] - Loss introduced by StarGANv2-VC to improve target speaker identity in converted speech.
- [[asr-speech-consistency-loss]] - ASR-feature loss used to preserve linguistic content during conversion.
- [[arousal-based-emotion-control]] - Continuous arousal-based control of emotional activation or intensity.
- [[autoencoder-voice-conversion]] - Encoder-decoder voice conversion that separates content from speaker/style information.
- [[cyclegan-evc]] - CycleGAN-based emotional voice conversion with non-parallel emotion-domain training.
- [[cwt-f0-modelling]] - Multi-scale F0 representation using continuous wavelet transform.
- [[diffusion-based-emotion-conversion]] - Diffusion-model approach to emotional speech conversion and related emotional speech generation.
- [[diffusion-emotion-mixing]] - Runtime mixing of diffusion denoising predictions from multiple emotion conditions.
- [[deep-emotional-features]] - SER-derived continuous emotion descriptors used for emotional style transfer.
- [[discrete-speech-units-for-evc]] - Learned speech units used for alignment-free emotional voice conversion.
- [[duration-flexible-evc]] - EVC that explicitly models duration and rhythm as part of emotion conversion.
- [[emotion-aware-acoustic-feature-loss]] - Emo-StarGAN loss comparing source and converted emotion-correlated acoustic descriptors.
- [[emotion-classifier-loss]] - Direct emotion supervision loss used by Emo-StarGAN when labels are available.
- [[emotion-embedding-loss]] - Emo-StarGAN loss comparing latent emotion representations of source and converted speech.
- [[emotion-intensity-control]] - Fine-grained control of how strongly a target emotion is expressed.
- [[emotion-preserving-voice-conversion]] - Speaker conversion that preserves the source utterance's emotion.
- [[emovoice-db]] - Synthetic English emotional speech dataset with natural-language emotion descriptions.
- [[emotional-speech-conversion]] - Conversion of speech toward emotional styles while preserving content.
- [[emovox]] - Sequence-to-sequence emotional voice conversion framework with emotion intensity control.
- [[evaluation-metrics-for-voice-conversion]] - Subjective and objective metrics used for naturalness, speaker similarity, and intelligibility.
- [[f0-consistency-loss]] - Pitch-contour preservation loss based on normalized F0.
- [[freestyle-emotion-prompting]] - Speech emotion control using natural-language affect descriptions rather than fixed class labels.
- [[information-bottleneck-for-voice-conversion]] - AutoVC bottleneck mechanism for balancing reconstruction and speaker disentanglement.
- [[in-the-wild-emotion-conversion]] - Emotional speech conversion on naturalistic non-parallel recordings with real-world variability.
- [[llm-based-emotional-tts]] - Emotional TTS approach that uses an LLM backbone to interpret text and emotion instructions.
- [[many-to-many-voice-conversion]] - Voice conversion among multiple source and target speaker domains.
- [[mapping-network]] - Latent-to-style module used for diverse target-domain style sampling.
- [[mixed-emotion-synthesis]] - Speech synthesis that expresses combinations of multiple emotional qualities.
- [[non-parallel-voice-conversion]] - Voice conversion trained without paired source-target utterances.
- [[relative-attributes-for-emotion-intensity]] - Ranking-based representation for emotion intensity without explicit intensity labels.
- [[sequence-to-sequence-emotional-voice-conversion]] - EVC approach that jointly models acoustic conversion and duration alignment.
- [[ser-perceptual-loss]] - Emotion supervision from a pretrained speech emotion recognizer.
- [[separate-vs-joint-prosody-training]] - Comparison of separate and joint learning for spectrum and prosody conversion.
- [[speaker-emotion-tradeoff]] - Evidence and open gaps around speaker conversion/anonymisation versus emotion preservation.
- [[speaker-disentanglement]] - Removing speaker identity from content representations while preserving conversion-relevant information.
- [[spectrum-prosody-conversion]] - Joint research concern of transforming spectral and prosodic emotion cues.
- [[speech-anonymisation]] - Modifying speech to remove speaker identity while preserving content.
- [[speaker-identity-evaluation-in-evc]] - Metrics and evidence for speaker preservation, similarity, or anonymisation in emotional voice conversion.
- [[stargan-v2]] - Multi-domain style transfer GAN adapted by StarGANv2-VC.
- [[style-pretraining-for-evc]] - Pretraining strategy using neutral multi-speaker speech before limited-data emotion training.
- [[style-encoder]] - Reference-based style extraction module.
- [[voice-conversion]] - General concept of changing voice identity or style while preserving linguistic content.
- [[phoneme-boosted-tts]] - TTS design that predicts phoneme tokens as auxiliary guidance for audio-token generation.
- [[pitch-conditioned-flow-matching]] - Flow matching VC conditioned on discrete pitch tokens for expressive prosody transfer.
- [[seen-and-unseen-emotion-transfer]] - Reference-conditioned transfer to emotion styles seen or unseen during conversion-model training.
- [[synthetic-emotional-speech-data]] - Emotional speech data generated by a model rather than recorded from human speakers.
- [[time-varying-timbre-tokens]] - Dynamic timbre representations used alongside global speaker embeddings.
- [[zero-shot-voice-conversion]] - Voice conversion involving speakers unseen during conversion-model training.
