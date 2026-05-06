# Diffusion Emotion Mixing

**Summary**: Diffusion emotion mixing combines denoising predictions from multiple emotion conditions during sampling. EmoMix uses this to synthesize mixed emotions without training on explicit mixed-emotion labels.

**Sources**:
- Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Definition

Diffusion emotion mixing combines noises predicted by a diffusion model under different emotion conditions during a single sampling process (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). In EmoMix, the mixture weights control the contribution of each emotion condition (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Run-time control

EmoMix first denoises with a base emotion condition, then introduces a mixed-in emotion condition during later sampling steps (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). The paper fixes mixing intervals in its mixed-emotion experiment and varies the mixture weight to represent weak, medium, and strong mixed-in intensity (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Strength

The main advantage is that new mixed-emotion conditions can be synthesized at run time without direct mixed-emotion training examples (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). EmoMix reports less CMOS degradation than MixedEmotion under weak, medium, and strong mixing settings (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Caution

This method is demonstrated for TTS in [[emomix]], not for voice conversion (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). Applying diffusion emotion mixing to VC would require separate evidence that content and speaker identity remain preserved.

## Related pages

- [[emomix]]
- [[mixed-emotion-synthesis]]
- [[diffusion-based-emotion-conversion]]
- [[emotion-intensity-control]]
