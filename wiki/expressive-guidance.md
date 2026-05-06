# Expressive Guidance

**Summary**: Expressive guidance is DiffEVC's inference-time method for strengthening target emotion transfer while controlling speaker and emotion conditioning. It is relevant to intensity-controlled emotional voice conversion because the guidance scale changes the strength of the generated emotional signal.

**Sources**:
- Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf

**Last updated**: 2026-05-06

---

## Definition

Expressive guidance is an inference-time conditioning method introduced by [[diffevc]] for any-to-any emotional voice conversion (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). It forms a guided condition by moving from a negative speaker-emotion condition toward a positive source-speaker/reference-emotion condition during diffusion sampling (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Intensity relevance

The guidance scale can be larger than 1, so the method can intensify the target emotion signal beyond simple categorical emotion replacement (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). This makes expressive guidance direct EVC evidence for [[emotion-intensity-control]], unlike many TTS-only intensity methods (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Tradeoff relevance

Expressive guidance should be interpreted through the [[speaker-emotion-tradeoff]], because making the emotion condition stronger can affect speaker similarity, naturalness, or quality (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). DiffEVC reports emotion conversion accuracy and SECS together for guidance variants, but it does not present a full guidance-strength Pareto curve over speaker similarity and emotion accuracy (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Related pages

- [[diffevc]]
- [[diffusion-based-emotion-conversion]]
- [[emotion-intensity-control]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
