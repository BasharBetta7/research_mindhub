# Tacotron

**Summary**: Tacotron is an end-to-end sequence-to-sequence TTS model that maps characters to spectrograms with attention. It is historical TTS backbone context, not emotional speech generation or EVC evidence.

**Sources**:
- Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Problem

Tacotron targets end-to-end text-to-speech synthesis that can be trained from text-audio pairs without hand-engineered linguistic features or an HMM aligner (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

The paper argues that traditional TTS pipelines contain separately trained components such as text frontend, duration model, acoustic model, and vocoder, which require domain expertise and can accumulate errors (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

## Method

Tacotron is a [[seq2seq-tts]] model with an encoder, attention-based decoder, and post-processing network (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

The model takes characters as input and predicts spectrogram frames, then uses Griffin-Lim reconstruction to synthesize waveform (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

The paper introduces CBHG modules, which combine one-dimensional convolution banks, highway networks, and bidirectional GRUs for sequence representation (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

Tacotron predicts multiple non-overlapping output frames at each decoder step, which reduces decoder length and helps attention alignment converge more quickly (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

## Results

Tacotron is trained on an internal North American English dataset with about 24.6 hours of professional female speech (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

The paper reports a 5-scale MOS of 3.82 +- 0.085 for Tacotron, compared with 3.69 +- 0.109 for a production parametric system and 4.09 +- 0.119 for a production concatenative system (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

## Relevance

Tacotron is useful background for sequence-to-sequence acoustic generation and attention alignment, which later affects emotional TTS and sequence-to-sequence EVC designs (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

It should not be cited as evidence for emotion intensity control, speaker preservation, or the [[speaker-emotion-tradeoff]], because it is a general TTS paper without emotional conditioning or EVC evaluation (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

## Related pages

- [[seq2seq-tts]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
- [[e3-tts]]
- [[glow-tts]]
