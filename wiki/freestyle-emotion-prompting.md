# Freestyle Emotion Prompting

**Summary**: Freestyle emotion prompting controls speech emotion with natural-language descriptions rather than fixed class labels. EmoVoice uses this interface for fine-grained emotional TTS, while PromptEVC uses it for controllable emotional voice conversion.

**Sources**:
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf

**Last updated**: 2026-05-08

---

## Definition

Freestyle emotion prompting means specifying the intended vocal affect with a natural-language description rather than a categorical label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). EmoVoice examples include descriptions such as supportive joy, desolation, foreboding, or disdain, paired with target text to synthesize (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

[[clapfm-evc]] extends this idea to emotional voice conversion by using natural-language prompts to obtain target emotion embeddings through [[evc-clap]] (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). This makes [[natural-language-emotion-control]] broader than emotional TTS alone.

[[promptevc]] extends freestyle prompting to direct EVC by using prompt descriptions to control emotion category, emotional intensity, mixed emotion, pitch, speaking speed, and volume (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). The paper gives prompt-based control as an alternative to labels, reference audios, and prespecified numeric factors (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Why it matters

The paper argues that fixed emotion labels are too coarse for subtle emotional states in speech (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). This is conceptually broader than [[emotion-intensity-control]], because a prompt can specify affective nuance, speaking attitude, and intensity-like cues without a single scalar intensity value (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

PromptEVC makes this distinction explicit in EVC: emotional intensity is evaluated as one prompt-controlled attribute, while pitch, speed, volume, and mixed emotion are also evaluated as separate prompt-controlled attributes (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Dataset design

In [[emovoice-db]], each emotional sample has a natural-language emotion description generated under constraints: the description should focus on vocal affect, avoid contextual event references, and be a single sentence rather than a single-word label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Evaluation risk

Freestyle prompts make automatic evaluation harder because the target is not just a class label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). The EmoVoice paper reports that emotion2vec similarity and multimodal LLM ratings have weak sentence-level alignment with human perception (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

ClapFM-EVC evaluates prompt-driven EVC with an ABX preference test against reference-driven conversion, but its reported main tables emphasize quality and emotion similarity rather than speaker identity preservation (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

PromptEVC reports automatic and human classification accuracy for prompt-controlled attributes, but it also illustrates the same tradeoff-evaluation gap because speaker identity is represented mainly by an F0-constrained speaker encoder and ablation rather than a dedicated speaker-similarity metric (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Related pages

- [[emovoice]]
- [[llm-based-emotional-tts]]
- [[emovoice-db]]
- [[emotion-intensity-control]]
- [[evaluation-metrics-for-voice-conversion]]
- [[natural-language-emotion-control]]
- [[clapfm-evc]]
- [[promptevc]]
- [[evc-clap]]
