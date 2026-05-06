# LLM-Based Emotional TTS

**Summary**: LLM-based emotional TTS uses a language model backbone to interpret text and emotion instructions before generating speech tokens. EmoVoice uses this approach to support fine-grained natural-language emotion prompting.

**Sources**:
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf

**Last updated**: 2026-05-06

---

## Definition

LLM-based emotional TTS adapts a pretrained language model to generate speech while conditioning on emotional instructions (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). In [[emovoice]], the LLM receives both the target sentence and a fine-grained emotion description, then predicts semantic audio tokens (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Rationale

The authors use an LLM backbone because natural-language emotion prompts require semantic understanding beyond fixed emotion-class labels (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). This makes the approach closely related to [[freestyle-emotion-prompting]].

## Implementation in EmoVoice

EmoVoice initializes its backbone from Qwen2.5 and expands the vocabulary with audio tokens for speech generation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). The model predicts grouped semantic audio tokens to shorten the generated sequence and accelerate training (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Caution

LLM initialization improves EmoVoice results, but the paper's evidence is within TTS rather than voice conversion (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). Applying the same idea to [[emotional-speech-conversion]] would require separate evidence.

## Related pages

- [[emovoice]]
- [[freestyle-emotion-prompting]]
- [[phoneme-boosted-tts]]
- [[synthetic-emotional-speech-data]]
- [[emotional-speech-conversion]]
