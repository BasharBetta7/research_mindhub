# Emotion Intensity Control

**Summary**: Emotion intensity control manipulates how strongly an emotion is expressed in converted speech. Zhou et al. 2023 argues that intensity should affect multiple prosodic cues rather than only loudness.

**Sources**:
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf
- Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf
- Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf
- Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf

**Last updated**: 2026-05-06

---

## Definition

Emotion intensity control aims to generate different strengths of the same target emotion, such as weak, medium, or strong expression (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). The paper evaluates intensity values 0.1, 0.5, and 0.9 as weak, medium, and strong settings (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Acoustic interpretation

The paper explicitly rejects reducing emotion intensity to loudness alone, because intensity can be observed through energy, speech rate, fundamental frequency, and prosodic dynamics (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). In Emovox visualizations, stronger angry and happy settings show higher F0 and larger F0 fluctuations, while stronger sad settings are more associated with slower speaking rate (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

The earlier [[transforming-spectrum-and-prosody-for-evc]] paper supports this view by treating F0 as hierarchical prosody and decomposing it with CWT across temporal scales (source: Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf).

[[freestyle-emotion-prompting]] is related but not identical to scalar intensity control, because a natural-language description can specify affective stance, vocal quality, and intensity-like nuance without an explicit numeric intensity value (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

[[arousal-based-emotion-control]] is another route to intensity control: [[emoconv-diff]] uses continuous arousal values from 1 to 7 as target emotion conditioning (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This is useful for activation strength, but it does not fully model valence or categorical emotion identity (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

[[prabhu-2023-in-the-wild-sec]] provides earlier direct EVC evidence for arousal-based control, using an arousal scalar as the emotion representation in SSL-disentangled HiFi-GAN resynthesis (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Methods

The paper compares scaling-factor control, attention-weight control, and [[relative-attributes-for-emotion-intensity]] (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). Relative attributes achieve better best-worst scaling results for intensity control and speech quality in the reported experiments (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

[[emomix]] controls primary emotion intensity in TTS by mixing neutral and target-emotion diffusion conditions in different proportions (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). This is adjacent evidence for controllable emotional speech, but not direct EVC evidence because EmoMix is text-to-speech rather than voice conversion (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

[[daisy-tts]] controls intensity in emotional TTS by scaling decomposed prosody embedding directions, where smaller scaling weakens emotion expression and larger scaling intensifies it (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). This is adjacent evidence that intensity can be represented through prosody-space manipulation rather than only through labels (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

[[clapfm-evc]] provides direct EVC evidence for adjustable intensity through an [[adaptive-intensity-gate]] that scales EVC-CLAP emotional features before fusion with content features (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). The ablation reports that removing AIG reduces speech quality and slightly reduces emotional similarity, so the mechanism appears important for the reported prompt-driven EVC system (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

[[emodiff]] controls emotional TTS intensity with [[soft-label-guidance]], where a target emotion receives weight alpha and neutral receives weight 1-alpha during classifier-guided diffusion sampling (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). This is useful adjacent evidence for continuous emotion-strength control, but it is not direct EVC evidence because EmoDiff is a TTS model (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

[[hierarchical-emotion-rendering]] expands intensity control from a single utterance-level value to [[hierarchical-emotion-control]] at utterance, word, and phoneme levels (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf). This is analytically important because emotion intensity can be localized inside an utterance, but the evidence remains TTS-adjacent rather than EVC-specific (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

[[einet]] provides direct EVC evidence for [[vad-based-emotion-intensity]], where VAD values are used to construct intensity pseudo-labels and to drive target-emotion intensity at inference (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf). Its controllability examples show broader pitch fluctuation, higher peak energy, stronger acoustic variation, and more short pauses as intensity increases (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

[[durflex-evc]] does not present an explicit scalar intensity control interface, but it is relevant because [[duration-flexible-evc]] models rhythm and duration, both of which can carry perceived intensity (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). [[pflow-vc]] is also adjacent because its discrete pitch conditioning targets expressive prosody transfer rather than a named intensity control variable (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Related pages

- [[emotion-intensity-and-control]]
- [[emovox]]
- [[relative-attributes-for-emotion-intensity]]
- [[emotional-speech-conversion]]
- [[f0-consistency-loss]]
- [[cwt-f0-modelling]]
- [[spectrum-prosody-conversion]]
- [[freestyle-emotion-prompting]]
- [[emovoice]]
- [[arousal-based-emotion-control]]
- [[emoconv-diff]]
- [[emomix]]
- [[mixed-emotion-synthesis]]
- [[duration-flexible-evc]]
- [[pitch-conditioned-flow-matching]]
- [[pflow-vc]]
- [[daisy-tts]]
- [[prosody-embedding-decomposition]]
- [[clapfm-evc]]
- [[adaptive-intensity-gate]]
- [[natural-language-emotion-control]]
- [[emodiff]]
- [[soft-label-guidance]]
- [[hierarchical-emotion-rendering]]
- [[hierarchical-emotion-control]]
- [[prabhu-2023-in-the-wild-sec]]
- [[einet]]
- [[vad-based-emotion-intensity]]
