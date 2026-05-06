# Text Guided Speech Infilling

**Summary**: Text-guided speech infilling generates missing speech from surrounding audio context and text. Voicebox uses this as a general training task for zero-shot TTS, editing, denoising, style transfer, and sampling.

**Sources**:
- Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf

**Last updated**: 2026-05-06

---

## Definition

Text-guided speech infilling predicts a masked segment of speech given surrounding audio context and the complete text transcript (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

In [[voicebox]], the surrounding audio provides style context and the transcript specifies linguistic content (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Why it matters

This training task lets a speech generation model perform multiple downstream tasks through in-context learning, including zero-shot TTS, denoising, content editing, style conversion, and diverse sampling (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

For this wiki, the concept is useful background for prompt/context-driven speech generation, but it is not direct evidence for independently controlled emotional voice conversion (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Related pages

- [[voicebox]]
- [[flow-matching-evc]]
- [[natural-language-emotion-control]]
- [[evaluation-metrics-for-voice-conversion]]
