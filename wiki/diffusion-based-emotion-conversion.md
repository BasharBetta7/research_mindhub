# Diffusion-Based Emotion Conversion

**Summary**: Diffusion-based emotion conversion uses a diffusion generative model to synthesize speech conditioned on content, speaker, and emotion representations. EmoConv-Diff applies this to non-parallel, in-the-wild speech emotion conversion.

**Sources**:
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf

**Last updated**: 2026-05-06

---

## Definition

Diffusion-based emotion conversion uses a reverse diffusion process to generate emotional speech conditioned on target emotion information (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). In [[emoconv-diff]], the diffusion decoder converts mel spectrograms while conditioning on phoneme, speaker, and emotion encodings (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

## Relation to TTS diffusion

[[emomix]] uses diffusion for emotional TTS rather than voice conversion, but it shows how diffusion sampling can support mixed emotion and intensity control at run time (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). This makes diffusion a shared modelling family across emotional TTS and emotional voice conversion, even though the input-output tasks differ.

[[clapfm-evc]] is related but uses conditional flow matching rather than a denoising diffusion decoder (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). It is therefore better linked through [[flow-matching-evc]] than treated as a diffusion-based EVC system.

## Why it matters

EmoConv-Diff uses diffusion to avoid requiring parallel source-target emotion pairs during training (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This is important for [[in-the-wild-emotion-conversion]], where clean parallel emotional references are not available (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

## Related pages

- [[emoconv-diff]]
- [[emomix]]
- [[diffusion-emotion-mixing]]
- [[in-the-wild-emotion-conversion]]
- [[emotional-speech-conversion]]
- [[clapfm-evc]]
- [[flow-matching-evc]]
