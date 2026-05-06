# End To End Diffusion TTS

**Summary**: End-to-end diffusion TTS directly generates speech waveform from text with a diffusion model. E3 TTS is the current wiki example and should be treated as architectural background for emotional speech generation.

**Sources**:
- Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf

**Last updated**: 2026-05-06

---

## Definition

End-to-end diffusion TTS uses a diffusion model to synthesize waveform directly from text, rather than first predicting an intermediate acoustic representation such as a mel-spectrogram (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

E3 TTS implements this by using BERT text representations and a 1D U-Net diffusion model over waveform samples (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

## Relevance

This concept is useful for understanding diffusion speech-generation backbones that could later be adapted to emotional TTS or EVC (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

The concept is not itself evidence for emotion control, because E3 TTS does not propose an emotional conditioning method (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

## Related pages

- [[e3-tts]]
- [[diffusion-based-emotion-conversion]]
- [[emodiff]]
- [[emomix]]
