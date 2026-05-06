# Emotion2vec

**Summary**: Emotion2vec is a self-supervised speech emotion representation used as an emotion-similarity proxy in several emotional speech generation papers. The wiki treats it as useful but not equivalent to human perception.

**Sources**:
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf

**Last updated**: 2026-05-06

---

## Definition

Emotion2vec provides speech emotion embeddings that can be used for emotion similarity or emotion consistency evaluation (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). In [[pflow-vc]], an emotion2vec-derived emotion consistency score is used to evaluate emotion style transfer (source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf).

## Evaluation Caution

[[emovoice]] reports that emotion2vec similarity has high system-level Spearman correlation with human ratings but much weaker sentence-level correlation of 0.4047 (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). This means emotion2vec is useful for comparing systems, but individual sample-level claims should still be checked with human listening tests (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

[[tf-mamba-ser]] is not emotion2vec, but it reinforces the same metric lesson: learned SER representations can become stronger by modelling temporal and frequency cues, yet they still remain automatic proxies for emotion perception (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## Related pages

- [[evaluation-metrics-for-voice-conversion]]
- [[ser-perceptual-loss]]
- [[emovoice]]
- [[pflow-vc]]
- [[tf-mamba-ser]]
- [[temporal-frequency-ser]]
