# Pitch-Conditioned Flow Matching

**Summary**: Pitch-conditioned flow matching uses pitch tokens as conditions for a flow matching decoder. PFlow-VC uses masked discrete pitch conditioning to improve expressive voice conversion.

**Sources**:
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf

**Last updated**: 2026-05-06

---

## Definition

Pitch-conditioned flow matching conditions a flow matching generative decoder on pitch representations during mel-spectrogram synthesis (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). In [[pflow-vc]], these pitch representations are discrete tokens from a pitch VQ-VAE trained on speaker-mean-normalized log F0 (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Why pitch is discrete

The paper argues that raw F0 contains speaker information, so it models speaker-mean-normalized log F0 to make pitch information more speaker-independent (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). Discrete pitch tokens are then used with masked training so the model learns pitch context from prompt speech (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Evidence

Removing pitch tokens from PFlow-VC worsens WER from 2.574 to 3.014 and SECS from 0.920 to 0.907 in the ablation study (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). The authors also report negative comparative MOS when pitch tokens are removed (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Related pages

- [[pflow-vc]]
- [[time-varying-timbre-tokens]]
- [[spectrum-prosody-conversion]]
- [[f0-consistency-loss]]
- [[speaker-emotion-tradeoff]]
