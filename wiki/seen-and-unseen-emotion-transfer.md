# Seen And Unseen Emotion Transfer

**Summary**: Seen and unseen emotion transfer tests whether an EVC model can transfer emotions present or absent during conversion-model training. DeepEST evaluates unseen angry transfer using SER-derived reference style features.

**Sources**:
- Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf

**Last updated**: 2026-05-06

---

## Definition

Seen emotion transfer converts to emotion styles included during training, while unseen emotion transfer converts to an emotion style not used to train the conversion model (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). [[deepest]] evaluates happy and sad as seen emotions and angry as an unseen emotion (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf).

## DeepEST evidence

DeepEST can use reference utterances to compute a mean deep emotional feature for a target emotion at run time (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). The paper reports that unseen neutral-to-angry conversion remains comparable to a VAW-GAN-EVC baseline trained with angry speech samples (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf).

## Caution

Unseen transfer is not the same as arbitrary emotion generalization, because DeepEST still relies on reference utterances and SER features for the target emotion (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). The claim should be understood as reference-conditioned unseen style transfer.

## Related pages

- [[deepest]]
- [[deep-emotional-features]]
- [[emotional-speech-conversion]]
- [[non-parallel-voice-conversion]]
