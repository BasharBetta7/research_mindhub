# Voicebox

**Summary**: Voicebox is a large-scale text-guided speech infilling model trained with flow matching. It is useful background for generalist speech generation and flow-matching backbones, but it is not direct EVC or emotion-speaker tradeoff evidence.

**Sources**:
- Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf

**Last updated**: 2026-05-06

---

## Problem

Voicebox targets general-purpose text-guided speech generation, where a single model can perform tasks such as zero-shot TTS, speech denoising, speech editing, style conversion, and diverse sample generation through in-context learning (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

The paper argues that many prior speech generation systems are task-specific, trained on curated small-scale datasets, or require labels for speaker, emotion, or noise style (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Method

Voicebox is trained on [[text-guided-speech-infilling]], where the model predicts masked speech given surrounding audio context and the full transcript (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

The model is a non-autoregressive continuous normalizing flow trained with flow matching using an optimal transport path (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

Voicebox decouples audio modeling from duration modeling, using forced alignments to build frame-level phonetic transcripts and using a HiFi-GAN vocoder to generate waveform from predicted mel-spectrograms (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Scale and tasks

The English Voicebox model is trained on 60K hours of ASR-transcribed English audiobooks, and the multilingual model is trained on 50K hours of multilingual audiobooks in six languages (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

The paper reports that Voicebox can use audio context to transfer style attributes such as voice, speaking style, emotion, and acoustic condition, but it does not provide independent control over those attributes (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Evaluation

The paper emphasizes reproducible model-based metrics: WER for correctness and intelligibility, embedding similarity for audio-context coherence, and Frechet Speech Distance for diversity and quality (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf). It also reports QMOS and SMOS as supplementary subjective metrics (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

For English zero-shot TTS with cross-sentence prompting, Voicebox reports WER 1.9, SIM-r 0.681, QMOS 3.78 +- 0.10, and SMOS 3.71 +- 0.11 (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf). The paper states that Voicebox outperforms VALL-E on WER and audio similarity and can be up to 20 times faster (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Caution

Voicebox is relevant to [[flow-matching-evc]] as large-scale speech generation background, but it is not an emotional voice conversion model (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

The paper explicitly notes that Voicebox does not allow independent control of voice, speaking style, emotion, and acoustic condition, so it should not be used as evidence that prompt-based style transfer solves the [[speaker-emotion-tradeoff]] (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Related pages

- [[text-guided-speech-infilling]]
- [[flow-matching-evc]]
- [[evaluation-metrics-for-voice-conversion]]
- [[speaker-emotion-tradeoff]]
- [[e3-tts]]
- [[tacotron]]
