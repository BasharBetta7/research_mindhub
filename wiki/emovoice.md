# EmoVoice

**Summary**: EmoVoice is an LLM-based emotional text-to-speech model that uses freestyle natural-language emotion prompts. It is relevant to this wiki as adjacent evidence about fine-grained emotion control, synthetic emotional speech data, and the limits of automatic emotion evaluation.

**Sources**:
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf

**Last updated**: 2026-05-06

---

## Problem framing

EmoVoice targets emotion-controllable TTS where the user gives a natural-language emotion description rather than a single categorical emotion label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). The authors argue that labels such as happy or sad are too coarse for nuanced emotional speech generation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

This paper is not a voice-conversion paper, so it should not be treated as direct evidence about [[speaker-emotion-tradeoff]] in VC (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). Its strongest relevance is to [[freestyle-emotion-prompting]], [[synthetic-emotional-speech-data]], and [[evaluation-metrics-for-voice-conversion]].

## Model

EmoVoice uses Qwen2.5 as an LLM backbone and autoregressively predicts CosyVoice semantic audio tokens, which are converted into waveforms using CosyVoice's flow matching module and HiFi-GAN vocoder (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). Its input format combines an emotion description and target text, such as an instruction to say a sentence with a described emotion (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

The paper also proposes EmoVoice-PP, a [[phoneme-boosted-tts]] variant that predicts phoneme tokens in parallel with audio tokens to improve content consistency (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Data

The paper introduces [[emovoice-db]], a 40.45-hour English emotional speech dataset with 22,100 synthetic samples across seven emotion categories (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). The dataset includes natural-language emotion descriptions and is generated using GPT-4o models, including GPT-4o-audio for speech synthesis (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

This is a useful data-scaling strategy, but it also means the training data is distilled from a teacher model rather than collected from human speakers (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). Any claim that EmoVoice-DB covers real human emotional speech variation should be marked as needing verification.

## Results

On the EmoVoice-DB test set, EmoVoice 1.5B reports WER 2.62, emotion similarity 0.9118, recall 0.424, and UTMOS 4.35, while GPT-4o-mini-tts reports WER 2.40, emotion similarity 0.9168, recall 0.456, and UTMOS 4.06 (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). In subjective evaluation, EmoVoice 1.5B reports MOS 3.507, compared with 3.598 for GPT-4o-mini-tts and 4.350 for GPT-4o-audio ground-truth synthetic speech (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

Scaling the LLM from 0.5B to 1.5B improves WER from 2.73 to 2.62 and recall from 0.395 to 0.424 on the fine-tuned emotional TTS setting (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). The improvement is real but modest compared with the extra model size, which matters for resource planning.

## Evaluation warning

The paper finds that emotion2vec emotion similarity has high system-level Spearman correlation with human ratings but much lower sentence-level correlation, 0.4047 (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). GPT-4o-audio and Gemini ratings also show low sentence-level correlations of 0.2569 and 0.1960, respectively (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

This supports a caution already present in [[evaluation-metrics-for-voice-conversion]]: automatic metrics may rank systems roughly but fail on fine-grained sample-level emotional quality (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Related pages

- [[llm-based-emotional-tts]]
- [[freestyle-emotion-prompting]]
- [[emovoice-db]]
- [[phoneme-boosted-tts]]
- [[synthetic-emotional-speech-data]]
- [[emotional-speech-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
