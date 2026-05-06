# End-To-End Generative EVC

**Summary**: End-to-end generative EVC synthesizes converted speech directly through a learned generative model rather than using a separate neutral vocoder pipeline. SGEVC is the current wiki example.

**Sources**:
- Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf

**Last updated**: 2026-05-06

---

## Definition

End-to-end generative EVC models the conversion path from conditioning variables to waveform synthesis inside one generative framework (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). SGEVC argues that using spectral features as an intermediate representation plus a separate neutral vocoder can harm synthesis quality, and instead adapts a VITS-style end-to-end framework (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Method example

[[sgevc]] combines a text-conditioned prior, a VC encoder, normalizing flows, and a HiFi-GAN decoder (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). This makes the model different from feature-mapping pipelines that convert WORLD or Mel-cepstral features and then synthesize speech with a separate vocoder (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Related pages

- [[sgevc]]
- [[semi-supervised-evc]]
- [[non-parallel-voice-conversion]]
- [[speaker-disentanglement]]
- [[evaluation-metrics-for-voice-conversion]]
