# Relative Attributes For Emotion Intensity

**Summary**: Relative attributes model emotion intensity as an ordered attribute between neutral and emotional speech. Emovox uses this method to control intensity without explicit intensity labels.

**Sources**:
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Definition

Relative attributes represent emotion intensity by learning a ranking function over acoustic features (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). Emovox treats neutral speech as zero intensity and learns that emotional samples should rank above neutral samples for the corresponding emotion category (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Training signal

The method forms ordered pairs from emotional and neutral samples, where emotional samples are assumed to have higher intensity than neutral samples (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). It also forms similar pairs from neutral-neutral and emotional-emotional samples, where the pair is assumed to have similar intensity (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Role in Emovox

The learned ranking function predicts a relative attribute normalized to the range 0 to 1, where larger values represent stronger emotion intensity (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). This value is passed through a fully connected layer to produce the intensity embedding used by [[emovox]] (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Related pages

- [[emotion-intensity-control]]
- [[emovox]]
- [[sequence-to-sequence-emotional-voice-conversion]]
