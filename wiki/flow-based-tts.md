# Flow Based TTS

**Summary**: Flow-based TTS uses invertible generative flows to synthesize acoustic representations from text conditions. Glow-TTS is the current wiki example and should be distinguished from conditional flow matching EVC.

**Sources**:
- Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf

**Last updated**: 2026-05-06

---

## Definition

Flow-based TTS uses generative normalizing flows to model the distribution of speech features conditioned on text (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

In Glow-TTS, a flow-based decoder maps between mel-spectrograms and latent variables, while a text encoder and duration predictor provide the text-side conditioning (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf).

## Relation to flow matching

Flow-based TTS should not be conflated with [[flow-matching-evc]]: Glow-TTS uses normalizing flows, while ClapFM-EVC and PFlow-VC use conditional flow matching objectives for conversion or expressive VC (source: Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf; source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Related pages

- [[glow-tts]]
- [[monotonic-alignment-search]]
- [[flow-matching-evc]]
