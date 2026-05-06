# E3 TTS

**Summary**: E3 TTS is an end-to-end diffusion TTS system that generates waveform directly from plain text. It is useful background for diffusion speech generation, but it is not an emotional TTS or EVC method.

**Sources**:
- Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf

**Last updated**: 2026-05-06

---

## Problem

E3 TTS targets end-to-end text-to-speech synthesis that directly maps plain text to waveform without an explicit intermediate mel-spectrogram stage (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

The paper argues that many previous diffusion TTS systems still rely on intermediate acoustic features or additional conditioning information, while E3 TTS relies on diffusion to model waveform temporal structure directly (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

## Method

E3 TTS uses a pretrained BERT model to extract text representations and a 1D U-Net diffusion model to iteratively refine noisy waveform samples into speech (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

The model is non-autoregressive and directly outputs waveform, which makes it an example of [[end-to-end-diffusion-tts]] (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

The paper also demonstrates prompt-based TTS and text-based speech editing without additional task-specific training, because alignment between text and waveform is dynamically determined during inference (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

## Results

On a proprietary single-speaker dataset, E3 TTS reports MOS 4.24 +- 0.06, compared with ground truth 4.56 +- 0.04 and Wave-Tacotron 4.07 +- 0.06 (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

The paper reports SQuId and speaker-similarity scores for audio-prompt TTS and text-based editing, using a speaker embedding model for speaker similarity (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf). It also reports that speaker-identification accuracy improves when more diffusion timesteps are sampled in a zero-shot speaker-similarity task (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

## Caution

E3 TTS should be used as architectural background for diffusion speech generation, not as direct evidence for emotional speech generation, emotional voice conversion, or the [[speaker-emotion-tradeoff]] (source: Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf).

## Related pages

- [[end-to-end-diffusion-tts]]
- [[diffusion-based-emotion-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
