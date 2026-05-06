# Seq2Seq TTS

**Summary**: Seq2Seq TTS maps text to acoustic frames with an encoder-decoder attention model. Tacotron is the current wiki example and provides historical background for later sequence-to-sequence emotional speech systems.

**Sources**:
- Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Definition

Seq2Seq TTS uses a sequence-to-sequence encoder-decoder architecture with attention to map text input into acoustic output frames (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

Tacotron implements this pattern by encoding character input, decoding mel-spectrogram frames with attention, and converting predicted spectrograms to waveform with a post-processing network and Griffin-Lim reconstruction (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

## Relation to EVC

Seq2Seq TTS is not the same task as [[sequence-to-sequence-emotional-voice-conversion]], but it is relevant background because both involve attention, alignment, duration, and acoustic-frame generation (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

The concept should be kept separate from EVC evidence unless a source explicitly adapts the architecture to voice conversion or emotional conversion (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf).

## Related pages

- [[tacotron]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[duration-flexible-evc]]
- [[evaluation-metrics-for-voice-conversion]]
