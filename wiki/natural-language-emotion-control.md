# Natural-Language Emotion Control

**Summary**: Natural-language emotion control uses text prompts to specify target emotional expression. EmoVoice applies this to emotional TTS, while ClapFM-EVC and PromptEVC apply it directly to emotional voice conversion.

**Sources**:
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf
- Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf

**Last updated**: 2026-05-08

---

## Definition

Natural-language emotion control specifies the desired vocal affect with free-form text rather than a fixed categorical emotion label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). In [[clapfm-evc]], natural-language prompts are used to drive emotional voice conversion by producing target emotional embeddings through EVC-CLAP (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

[[promptevc]] also uses natural-language prompts for direct EVC, but it maps prompts through a RoBERTa emotion descriptor and diffusion-based prompt mapper trained against Emotion2Vec reference embeddings (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). This makes PromptEVC a prompt-only control route, while [[clapfm-evc]] supports both prompt-driven and reference-driven conversion (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf; source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Why It Matters

Natural-language control can describe fine-grained emotion beyond a limited label set (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). ClapFM-EVC uses this interface for EVC and supports prompt-driven conversion, reference-driven conversion, and prompt-based retrieval of reference speech (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

PromptEVC extends the same interface to multiple controllable speech attributes, including emotion category, emotional intensity, mixed emotion, pitch, speaking speed, and volume (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). Its controllability evaluation reports classifier and human-annotation accuracy for these attributes, including emotional intensity and mixed emotion (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Evaluation Caution

Natural-language targets make evaluation harder because the target emotion is a semantic description rather than a single class label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). ClapFM-EVC evaluates prompt-driven control with ABX preference tests against reference-driven conversion, but its main reported metrics still focus on quality and emotion similarity rather than speaker drift (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

PromptEVC reports controllability for intensity, mixed emotion, pitch, speed, and volume, but its speaker-identity evidence remains indirect because the main evaluation does not include a standard speaker-similarity metric such as SECS, EER, or sMOS (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Related pages

- [[freestyle-emotion-prompting]]
- [[emovoice]]
- [[clapfm-evc]]
- [[promptevc]]
- [[evc-clap]]
- [[emotion-intensity-control]]
