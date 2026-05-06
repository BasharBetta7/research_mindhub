# Glow-TTS

**Summary**: Glow-TTS is a flow-based parallel TTS model that learns alignments with Monotonic Alignment Search. It is useful background for flow-based speech generation, but it is not an emotional voice-conversion method.

**Sources**:
- Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf

**Last updated**: 2026-05-06

---

## Problem

Glow-TTS targets parallel TTS generation without requiring an external autoregressive aligner (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

The paper argues that earlier parallel TTS systems often needed guidance from autoregressive models, while Glow-TTS learns its own hard monotonic alignment between text and speech latents (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

## Method

Glow-TTS uses a text encoder, duration predictor, and flow-based decoder, making it a central example of [[flow-based-tts]] (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

The key alignment mechanism is [[monotonic-alignment-search]], which uses dynamic programming to find the most probable monotonic alignment between text tokens and latent speech representations during training (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf). At inference, Glow-TTS uses the trained duration predictor rather than running monotonic alignment search again (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

## Results

On single-speaker LJSpeech, Glow-TTS with temperature 0.333 reports MOS 4.01 +- 0.08, compared with Tacotron 2 MOS 3.88 +- 0.08 and ground-truth vocoded speech MOS 4.19 +- 0.07 (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

Glow-TTS reports 15.7 times faster synthesis than Tacotron 2 on average, and its inference time remains nearly constant as input length grows in the reported speed experiment (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

In the multi-speaker setting, the best Glow-TTS configuration reports MOS 3.45 +- 0.11, which the authors describe as comparable to Tacotron 2 (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

## Relation to voice conversion

Glow-TTS includes a voice-conversion-style experiment where a ground-truth mel-spectrogram is mapped into a latent representation with the source speaker identity and inverted with a different target speaker identity (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

This experiment is useful background for speaker disentanglement in flow-based TTS, but Glow-TTS is not an emotional voice-conversion model and does not study emotion preservation or speaker drift under emotion conversion (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

## Related pages

- [[flow-based-tts]]
- [[monotonic-alignment-search]]
- [[voice-conversion]]
- [[speaker-disentanglement]]
- [[evaluation-metrics-for-voice-conversion]]
