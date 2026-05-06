# Monotonic Alignment Search

**Summary**: Monotonic Alignment Search is Glow-TTS's dynamic-programming procedure for finding the most probable monotonic alignment between text tokens and latent speech frames. It removes the need for an external autoregressive aligner during Glow-TTS training.

**Sources**:
- Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf

**Last updated**: 2026-05-06

---

## Definition

Monotonic Alignment Search searches for the most probable monotonic alignment between a text sequence and the latent representation of speech (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

Glow-TTS uses this search during training to estimate hard alignments, then trains a duration predictor to reproduce those alignments during inference (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

## Why it matters

The mechanism lets Glow-TTS train as a parallel TTS model without relying on an external aligner from an autoregressive TTS model (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

For the emotion-generation wiki, this is mainly background for alignment and duration modelling rather than direct evidence about emotional control or speaker drift (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

## Related pages

- [[glow-tts]]
- [[flow-based-tts]]
- [[duration-flexible-evc]]
- [[sequence-to-sequence-emotional-voice-conversion]]
