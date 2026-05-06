# Natural-Language Emotion Control

**Summary**: Natural-language emotion control uses text prompts to specify target emotional expression. EmoVoice applies this to emotional TTS, while ClapFM-EVC applies it directly to emotional voice conversion.

**Sources**:
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf

**Last updated**: 2026-05-06

---

## Definition

Natural-language emotion control specifies the desired vocal affect with free-form text rather than a fixed categorical emotion label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). In [[clapfm-evc]], natural-language prompts are used to drive emotional voice conversion by producing target emotional embeddings through EVC-CLAP (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Why It Matters

Natural-language control can describe fine-grained emotion beyond a limited label set (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). ClapFM-EVC uses this interface for EVC and supports prompt-driven conversion, reference-driven conversion, and prompt-based retrieval of reference speech (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Evaluation Caution

Natural-language targets make evaluation harder because the target emotion is a semantic description rather than a single class label (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). ClapFM-EVC evaluates prompt-driven control with ABX preference tests against reference-driven conversion, but its main reported metrics still focus on quality and emotion similarity rather than speaker drift (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Related pages

- [[freestyle-emotion-prompting]]
- [[emovoice]]
- [[clapfm-evc]]
- [[evc-clap]]
- [[emotion-intensity-control]]

