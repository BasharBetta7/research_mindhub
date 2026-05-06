# Emotion Embedding Loss

**Summary**: Emotion embedding loss compares latent emotion representations of source and converted speech. Emo-StarGAN uses it as indirect supervision and finds it contributes strongly to emotion preservation.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Emotion embedding loss penalizes the mean absolute error between the latent emotion embedding of the source utterance and that of the converted utterance (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). In [[emo-stargan]], this is an indirect emotion supervision signal because it can compare source and converted samples through learned emotion representations (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Training setup

The embeddings are obtained through a two-stage process: first a StarGANv2-VC-style emotion conversion model learns emotion embeddings, then the emotion style encoder is fine-tuned for automatic embedding extraction (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). The fine-tuned model produces a 64-dimensional latent emotion representation used during voice conversion training (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Evidence

The Emo-StarGAN ablation reports that emotion embedding loss alone reaches 51.0% Accorig and 81.3 PCC, compared with the baseline's 20.2% Accorig and 78.9 PCC (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). The authors state that this loss contributes the most to emotion preservation among their individual proposed losses (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Related pages

- [[emo-stargan]]
- [[emotion-preserving-voice-conversion]]
- [[emotion-classifier-loss]]
- [[emotion-aware-acoustic-feature-loss]]
