# Flow Matching EVC

**Summary**: Flow matching EVC uses conditional flow matching to generate converted speech features. ClapFM-EVC uses a flow-matching decoder for prompt- or reference-controlled EVC, while PFlow-VC uses flow matching for expressive voice conversion.

**Sources**:
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf

**Last updated**: 2026-05-06

---

## Definition

Flow matching EVC uses a conditional flow matching model to reconstruct or generate mel-spectrogram features under content, speaker, prosody, or emotion conditions (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). This is related to diffusion-style generation but uses flow matching rather than denoising diffusion sampling (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## ClapFM-EVC

[[clapfm-evc]] uses an optimal-transport conditional flow matching decoder conditioned on EVC-CLAP emotional embeddings to reconstruct target mel-spectrograms (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). During inference, it samples the target mel-spectrogram with 25 Euler steps and sends it to a pretrained vocoder (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## PFlow-VC

[[pflow-vc]] uses a masked pitch-conditioned flow matching model for expressive voice conversion with discrete pitch tokens and target speaker prompt information (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). This makes flow matching a recurring modelling family for expressive conversion and EVC-adjacent systems.

## Related pages

- [[clapfm-evc]]
- [[pflow-vc]]
- [[pitch-conditioned-flow-matching]]
- [[diffusion-based-emotion-conversion]]
- [[emotional-speech-conversion]]

