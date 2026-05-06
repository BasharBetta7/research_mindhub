# Time-Varying Timbre Tokens

**Summary**: Time-varying timbre tokens represent dynamic speaker characteristics rather than only a global speaker embedding. PFlow-VC uses them to improve zero-shot speaker similarity.

**Sources**:
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf

**Last updated**: 2026-05-06

---

## Definition

Time-varying timbre tokens are local speaker representations intended to capture speaker traits that vary over time with content and pitch (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). PFlow-VC combines them with a global speaker embedding (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Evidence

The PFlow-VC ablation without time-varying timbre tokens reduces SECS from 0.920 to 0.877 and gives a large negative speaker-similarity CMOS of -0.41 (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). This suggests that a single global speaker embedding can be insufficient for robust timbre preservation in zero-shot VC (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Relation to speaker-emotion tradeoff

Better timbre modeling matters for [[speaker-emotion-tradeoff]] because expressive or emotional style transfer can otherwise drift away from the target speaker identity (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). However, PFlow-VC does not provide a systematic Pareto frontier between timbre preservation and emotion strength.

## Related pages

- [[pflow-vc]]
- [[pitch-conditioned-flow-matching]]
- [[speaker-emotion-tradeoff]]
- [[speaker-disentanglement]]
