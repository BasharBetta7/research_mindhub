# Semi-Supervised EVC

**Summary**: Semi-supervised EVC uses a small amount of labeled emotional speech together with unlabeled or weakly labeled speech. SGEVC is the main wiki source, showing that emotion control can be learned with limited supervised labels.

**Sources**:
- Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf

**Last updated**: 2026-05-06

---

## Definition

Semi-supervised EVC reduces dependence on fully labeled emotional datasets by combining supervised emotion-label losses with unsupervised generative learning (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). This is useful because emotion labels are time-consuming and labor-intensive to annotate (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## SGEVC method

[[sgevc]] uses an observed speaker identity variable and a categorical latent emotion variable, with supervised cross-entropy when labels are available and an unsupervised variational objective when they are not (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). The method uses Gumbel-Softmax to sample the emotion attribute and a modified KL term to prevent the emotion latent from collapsing into the prior (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Tradeoff relevance

Semi-supervised EVC is relevant to [[speaker-emotion-tradeoff]] when the model explicitly separates speaker identity from emotion labels or latent emotion variables (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). SGEVC makes that separation architecturally explicit, but its reported results do not yet quantify speaker drift with a speaker-similarity metric after conversion (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Related pages

- [[sgevc]]
- [[speaker-disentanglement]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[non-parallel-voice-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
