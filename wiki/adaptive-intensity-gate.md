# Adaptive Intensity Gate

**Summary**: The adaptive intensity gate is the ClapFM-EVC mechanism for adjusting emotion intensity during conversion. It scales EVC-CLAP emotional features before they are fused with content features.

**Sources**:
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf

**Last updated**: 2026-05-06

---

## Definition

The adaptive intensity gate is a module in ClapFM-EVC's FuEncoder that multiplies EVC-CLAP emotional features by a learnable hyperparameter to adjust emotional intensity (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). It is used before the adaptive fusion module combines emotional features with PPG content features (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Evaluation Role

The ClapFM-EVC ablation reports that removing AIG reduces speech quality and slightly reduces emotional similarity, which the paper interprets as evidence that AIG helps integrate content and emotion (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Relation To Intensity Control

AIG is one of the clearest EVC-specific mechanisms in the wiki for explicit emotion intensity control, because it appears in a voice conversion framework rather than only emotional TTS (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Related pages

- [[clapfm-evc]]
- [[emotion-intensity-control]]
- [[evc-clap]]
- [[flow-matching-evc]]

