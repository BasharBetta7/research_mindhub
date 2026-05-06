# Phoneme-Boosted TTS

**Summary**: Phoneme-boosted TTS uses phoneme prediction as an auxiliary output to improve content consistency. EmoVoice-PP predicts phoneme and audio tokens in parallel.

**Sources**:
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf

**Last updated**: 2026-05-06

---

## Definition

Phoneme-boosted TTS adds phoneme-token prediction to guide audio-token generation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). In [[emovoice]], the EmoVoice-PP variant predicts phoneme tokens and semantic audio tokens in parallel (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Motivation

The paper frames phoneme prediction as intermediate guidance inspired by chain-of-thought and chain-of-modality ideas (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). Because phoneme tokens have a lower token rate than audio tokens, EmoVoice-PP can predict them earlier during inference and use them as supervision for audio generation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Evidence

In the pre-trained TTS setting, EmoVoice-PP reports WER 3.94 on the EmoVoice-DB test set and 3.11 on Seed-TTS test-en, outperforming the audio-only EmoVoice WERs of 4.73 and 3.31 (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). On the hard-case English test set, EmoVoice-PP reports WER 11.68, better than audio-only EmoVoice at 18.07 and parallel-text EmoVoice-PT at 16.34 (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Caution

The strongest benefit of EmoVoice-PP appears to be content consistency rather than a clear emotional-expressiveness gain, because emotion similarity and recall differences between output structures are small on the EmoVoice-DB test set (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Related pages

- [[emovoice]]
- [[llm-based-emotional-tts]]
- [[freestyle-emotion-prompting]]
- [[evaluation-metrics-for-voice-conversion]]
