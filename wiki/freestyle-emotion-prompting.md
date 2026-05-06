# Freestyle Emotion Prompting

**Summary**: Freestyle emotion prompting controls speech emotion with natural-language descriptions rather than fixed class labels. EmoVoice uses this interface for fine-grained emotional TTS.

**Sources**:
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf

**Last updated**: 2026-05-06

---

## Definition

Freestyle emotion prompting means specifying the intended vocal affect with a natural-language description rather than a categorical label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). EmoVoice examples include descriptions such as supportive joy, desolation, foreboding, or disdain, paired with target text to synthesize (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Why it matters

The paper argues that fixed emotion labels are too coarse for subtle emotional states in speech (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). This is conceptually broader than [[emotion-intensity-control]], because a prompt can specify affective nuance, speaking attitude, and intensity-like cues without a single scalar intensity value (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Dataset design

In [[emovoice-db]], each emotional sample has a natural-language emotion description generated under constraints: the description should focus on vocal affect, avoid contextual event references, and be a single sentence rather than a single-word label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Evaluation risk

Freestyle prompts make automatic evaluation harder because the target is not just a class label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). The EmoVoice paper reports that emotion2vec similarity and multimodal LLM ratings have weak sentence-level alignment with human perception (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Related pages

- [[emovoice]]
- [[llm-based-emotional-tts]]
- [[emovoice-db]]
- [[emotion-intensity-control]]
- [[evaluation-metrics-for-voice-conversion]]
