# Emotion Classifier Loss

**Summary**: Emotion classifier loss gives Emo-StarGAN direct emotion supervision when emotion labels are available. It trains a classifier on source emotion and then trains the generator to preserve that source emotion after conversion.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Emo-StarGAN adds an emotion classifier that predicts the source emotion of an utterance when emotion labels are available (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). When training the classifier, the generator is fixed and the classifier learns source-emotion classification; when training the generator, the classifier is fixed and the generator is encouraged to produce samples with the same emotion as the source (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Evidence and caveat

The ablation reports that emotion classifier loss alone improves Accorig from 20.2% to 49.3% and PCC from 78.9 to 81.0 (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). The authors suggest that the classifier may suffer from confirmation bias on noisy emotion labels, which may explain why [[emotion-embedding-loss]] contributes more in their ablation (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[emo-stargan]]
- [[emotion-preserving-voice-conversion]]
- [[emotion-embedding-loss]]
- [[emotion-aware-acoustic-feature-loss]]
