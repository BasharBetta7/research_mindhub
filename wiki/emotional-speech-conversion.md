# Emotional Speech Conversion

**Summary**: Emotional speech conversion changes speech style toward an emotional target while aiming to preserve content. StarGANv2-VC is relevant because it reports conversion from plain reading speech into emotional acting speech.

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

## Role in StarGANv2-VC

The StarGANv2-VC paper trains a model on 10 English speakers from the Emotional Speech Dataset with five emotions (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). The authors state that their framework can convert plain reading speech into emotive acting speech when trained on a corpus with diverse speech styles (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Analytical caution

The emotional speech claim is relevant but weaker than the paper's main VCTK speaker-conversion result, because the paper points readers to demo samples for emotional conversion rather than reporting the same subjective and objective metrics used for the main comparison with AUTO-VC (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

For research on emotion generation, [[evaluation-metrics-for-voice-conversion]] should probably be extended with emotion-specific measures, because the paper itself notes that common objective metrics can miss F0-related perceptual problems (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

## Emotion preservation

[[emo-stargan]] focuses on preserving source emotion during speaker conversion, rather than converting speech into a different target emotion (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). This distinction matters because [[emotion-preserving-voice-conversion]] evaluates whether rhythm, intonation, pauses, stresses, and intensity remain close to the source even after anonymising the speaker (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Emotion intensity

[[emotion-intensity-and-control]] studies emotional voice conversion where the target emotion category and the strength of expression are both controlled (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). This adds a useful axis to the wiki: emotional conversion can mean target-emotion generation, emotion preservation during anonymisation, or explicit [[emotion-intensity-control]] (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf; source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Spectrum and prosody

[[transforming-spectrum-and-prosody-for-evc]] argues that emotional voice conversion should transform both spectrum and prosody because emotion is manifested through hierarchical prosodic structure as well as spectral patterns (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf). This paper is an earlier non-parallel EVC result that motivates later work on [[emotion-intensity-control]] and [[sequence-to-sequence-emotional-voice-conversion]] (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf; source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Adjacent TTS evidence

[[emovoice]] is an emotional TTS paper rather than an emotional voice conversion paper, but it is relevant because it studies fine-grained natural-language emotion control with [[freestyle-emotion-prompting]] (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). This suggests a possible future direction for EVC interfaces, but it does not directly prove speaker-preserving or speaker-changing conversion performance (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## In-the-wild diffusion conversion

[[emoconv-diff]] directly studies speech emotion conversion on non-parallel in-the-wild data and is therefore stronger evidence for this page than emotional TTS papers (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). It converts continuous arousal while preserving lexical content and speaker identity, using separate phoneme, speaker, and emotion encoders with a diffusion decoder (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

[[emomix]] is also diffusion-based, but it is emotional TTS rather than VC; its value here is mainly as adjacent evidence for [[mixed-emotion-synthesis]] and [[diffusion-emotion-mixing]] (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Discrete and style-conditioned EVC

[[deepest]] introduced a one-to-many emotional style transfer framework using [[deep-emotional-features]] from SER and released ESD, which later EVC papers use as a benchmark (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). [[durflex-evc]] advances the ESD line by using [[discrete-speech-units-for-evc]] and [[duration-flexible-evc]] to avoid text alignment while modelling rhythm (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

[[pflow-vc]] is expressive VC rather than dedicated EVC, but its [[pitch-conditioned-flow-matching]] results are relevant because they evaluate emotion style consistency while preserving target speaker timbre (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Related pages

- [[starganv2-vc]]
- [[voice-conversion]]
- [[style-encoder]]
- [[f0-consistency-loss]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emo-stargan]]
- [[emotion-preserving-voice-conversion]]
- [[emotion-intensity-and-control]]
- [[emovox]]
- [[emotion-intensity-control]]
- [[transforming-spectrum-and-prosody-for-evc]]
- [[spectrum-prosody-conversion]]
- [[cwt-f0-modelling]]
- [[emovoice]]
- [[freestyle-emotion-prompting]]
- [[synthetic-emotional-speech-data]]
- [[emoconv-diff]]
- [[diffusion-based-emotion-conversion]]
- [[in-the-wild-emotion-conversion]]
- [[emomix]]
- [[mixed-emotion-synthesis]]
- [[deepest]]
- [[durflex-evc]]
- [[duration-flexible-evc]]
- [[discrete-speech-units-for-evc]]
- [[pflow-vc]]
