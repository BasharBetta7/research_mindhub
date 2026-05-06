# Mixed Emotion Synthesis

**Summary**: Mixed emotion synthesis generates speech that expresses more than one emotional quality. EmoMix uses diffusion noise mixing to synthesize mixed emotions and intensity variations.

**Sources**:
- Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Definition

Mixed emotion synthesis aims to generate speech with a combination of multiple emotions rather than a single primary emotion (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). EmoMix discusses examples such as combining happy and surprise as excitement (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Method in EmoMix

[[emomix]] performs mixed emotion synthesis through [[diffusion-emotion-mixing]], where predicted noises from multiple emotion conditions are combined during sampling (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). This avoids directly training a model on explicit mixed-emotion labels (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Relation to intensity

EmoMix also uses mixing between neutral and a primary emotion to control target emotion intensity (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). This makes mixed-emotion synthesis related to [[emotion-intensity-control]], but not identical to scalar control methods such as relative attributes.

## Caution

The paper analyzes mixed emotions partly with SER classifier probabilities (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). Because SER probabilities are proxies for perception, mixed-emotion claims should be interpreted cautiously unless supported by listening tests.

## Related pages

- [[emomix]]
- [[diffusion-emotion-mixing]]
- [[emotion-intensity-control]]
- [[ser-perceptual-loss]]
- [[evaluation-metrics-for-voice-conversion]]
