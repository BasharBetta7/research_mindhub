# VAD Based Emotion Intensity

**Summary**: VAD-based emotion intensity estimates emotional strength from valence, arousal, and dominance values rather than only acoustic-feature distances. EINet uses VAD-based pseudo-labels for controllable emotional voice conversion.

**Sources**:
- Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf

**Last updated**: 2026-05-06

---

## Definition

VAD-based emotion intensity uses valence, arousal, and dominance values to quantify an utterance's emotional state and derive intensity pseudo-labels (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

In [[einet]], an emotion evaluator predicts VAD values and an intensity mapper uses them to build controllable intensity pseudo-labels (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

## Motivation

The paper argues that measuring intensity only through distances between acoustic features can miss inherent emotional fluctuations of a speaker and create a mismatch between intensity modeling and run-time conversion (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

VAD values are intended to align intensity modeling more closely with emotional state, which helps the model produce more diverse and natural converted speech (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

## Relation to arousal control

VAD-based intensity is broader than [[arousal-based-emotion-control]] because it uses valence, arousal, and dominance rather than arousal alone (source: Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf).

## Related pages

- [[einet]]
- [[emotion-intensity-control]]
- [[arousal-based-emotion-control]]
- [[relative-attributes-for-emotion-intensity]]
- [[speaker-emotion-tradeoff]]
