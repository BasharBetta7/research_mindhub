# Emovox

**Summary**: Emovox is a sequence-to-sequence emotional voice conversion framework for controlling target emotion and emotion intensity. It combines linguistic, emotion, and intensity embeddings to generate converted emotional speech.

**Sources**:
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Architecture

Emovox consists of a recognition encoder, an emotion encoder, an intensity encoder, and a sequence-to-sequence decoder (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). The recognition encoder extracts linguistic embedding from source speech, the emotion encoder extracts emotion style from reference speech, the intensity encoder converts an intensity input into an intensity embedding, and the decoder generates converted speech from these representations (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

At run time, Emovox performs linguistic transplant from source speech, emotion transfer from reference speech, and [[emotion-intensity-control]] from either a reference-derived or manually provided intensity value (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Training

Emovox uses text and audio supervision during training so the recognition encoder and text encoder learn compatible linguistic embeddings (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). The decoder alternates between text-derived and audio-derived linguistic embeddings depending on the training epoch (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

The model uses [[style-pretraining-for-evc]] on VCTK and emotion training on ESD, with about 50 minutes of emotional training data in the reported setup (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). It also uses [[ser-perceptual-loss]] to improve emotional intelligibility of converted speech (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Evaluation

The paper compares Emovox with CycleGAN-EVC, StarGAN-EVC, and Seq2Seq-EVC for neutral-to-angry, neutral-to-happy, and neutral-to-sad conversion (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). Emovox reports lower MCD than CycleGAN-EVC and StarGAN-EVC across all three pairs, and better DDUR than Seq2Seq-EVC for neutral-to-angry and neutral-to-happy conversion (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Related pages

- [[emotion-intensity-and-control]]
- [[emotion-intensity-control]]
- [[relative-attributes-for-emotion-intensity]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[ser-perceptual-loss]]
- [[style-pretraining-for-evc]]
- [[emotional-speech-conversion]]
