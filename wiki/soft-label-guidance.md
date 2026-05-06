# Soft Label Guidance

**Summary**: Soft-label guidance adapts diffusion classifier guidance so emotional speech can be generated with a continuous intensity value rather than a one-hot emotion label. EmoDiff uses it to interpolate between neutral and a target emotion during sampling.

**Sources**:
- Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf

**Last updated**: 2026-05-06

---

## Definition

Soft-label guidance is EmoDiff's extension of classifier guidance for emotion intensity control in diffusion-based emotional TTS (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

Instead of guiding sampling with a one-hot emotion label, EmoDiff uses a soft label in which the target emotion has weight alpha and neutral has weight 1-alpha (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). The paper interprets alpha as emotion intensity, where alpha 0.0 corresponds to neutral and alpha 1.0 corresponds to the full target emotion (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

## Why it matters

Soft-label guidance avoids requiring a separately estimated intensity label during acoustic-model training because the intensity is supplied during the guided reverse diffusion process (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

The method connects [[emotion-intensity-control]] and [[mixed-emotion-synthesis]] because the same weighted-label idea can represent either neutral-to-target intensity or a combination of multiple target emotions (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

## Caution

Soft-label guidance is demonstrated in emotional TTS, so it should not be treated as confirmed EVC evidence unless a voice-conversion system adopts and evaluates the same mechanism (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

The reported intensity behavior is measured with a classifier-probability proxy, so human perception should remain the stronger test for fine-grained emotional intensity (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

## Related pages

- [[emodiff]]
- [[emotion-intensity-control]]
- [[mixed-emotion-synthesis]]
- [[diffusion-based-emotion-conversion]]
- [[ser-perceptual-loss]]
- [[relative-attributes-for-emotion-intensity]]
