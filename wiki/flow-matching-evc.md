# Flow Matching EVC

**Summary**: Flow matching EVC uses conditional flow matching to generate converted speech features. ClapFM-EVC uses a flow-matching decoder for prompt- or reference-controlled EVC, while PFlow-VC uses flow matching for expressive voice conversion.

**Sources**:
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf
- Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf
- Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf

**Last updated**: 2026-05-06

---

## Definition

Flow matching EVC uses a conditional flow matching model to reconstruct or generate mel-spectrogram features under content, speaker, prosody, or emotion conditions (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). This is related to diffusion-style generation but uses flow matching rather than denoising diffusion sampling (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## ClapFM-EVC

[[clapfm-evc]] uses an optimal-transport conditional flow matching decoder conditioned on EVC-CLAP emotional embeddings to reconstruct target mel-spectrograms (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). During inference, it samples the target mel-spectrogram with 25 Euler steps and sends it to a pretrained vocoder (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## PFlow-VC

[[pflow-vc]] uses a masked pitch-conditioned flow matching model for expressive voice conversion with discrete pitch tokens and target speaker prompt information (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). This makes flow matching a recurring modelling family for expressive conversion and EVC-adjacent systems.

## TTS background

[[hierarchical-emotion-rendering]] uses a Matcha-TTS-style optimal-transport conditional flow matching backbone for emotional TTS, so it is related architecturally but not an EVC system (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

[[voicebox]] is large-scale speech generation background for flow matching: it trains a non-autoregressive continuous normalizing flow with flow matching for text-guided speech infilling (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf). It is not an EVC method because it transfers style through audio context rather than independently controlling speaker and emotion attributes (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

[[glow-tts]] is also flow-related background, but it uses normalizing flows and [[monotonic-alignment-search]] rather than a conditional flow matching objective (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

## Related pages

- [[clapfm-evc]]
- [[pflow-vc]]
- [[pitch-conditioned-flow-matching]]
- [[diffusion-based-emotion-conversion]]
- [[emotional-speech-conversion]]
- [[hierarchical-emotion-rendering]]
- [[flow-based-tts]]
- [[glow-tts]]
- [[voicebox]]
- [[text-guided-speech-infilling]]
