# Emotion Intensity And Control

**Summary**: Zhou et al. 2023 studies fine-grained emotion intensity control for emotional voice conversion. The paper proposes Emovox, a sequence-to-sequence EVC framework that uses relative attributes, SER perceptual losses, and style pretraining.

**Sources**:
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Core idea

The paper argues that emotional voice conversion should control not only the target emotion category but also the intensity level of that emotion (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). It proposes [[emovox]], a [[sequence-to-sequence-emotional-voice-conversion]] framework that jointly models linguistic content, emotion style, and emotion intensity (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

The authors define emotional voice conversion as changing the emotional state of an utterance while preserving linguistic content and speaker identity (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). This differs from [[emotion-preserving-voice-conversion]], where the goal is to preserve the source emotion while changing speaker identity (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf; source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf).

## Emotion intensity

The paper states that emotion intensity is not just voice loudness, because it correlates with multiple acoustic cues including energy, speech rate, fundamental frequency, and prosodic dynamics (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). It uses [[relative-attributes-for-emotion-intensity]] to model fine-grained intensity without explicit intensity labels (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Training strategy

Emovox uses [[style-pretraining-for-evc]] on a multi-speaker TTS corpus to reduce the need for large emotional speech datasets (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). It also uses [[ser-perceptual-loss]] through emotion classification loss and emotion embedding similarity loss from a pretrained speech emotion recognizer (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Evidence and limitations

Emovox outperforms CycleGAN-EVC, StarGAN-EVC, and Seq2Seq-EVC in emotion similarity listening tests and generally improves MCD and DDUR in neutral-to-angry and neutral-to-happy conversion (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). Relative attributes outperform scaling factor and attention weight intensity control in best-worst scaling listening tests (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

The experiments mainly use neutral-to-angry, neutral-to-happy, and neutral-to-sad conversion with one male ESD speaker, so the generality of the intensity-control method across speakers, languages, and more complex emotions needs further verification (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Related pages

- [[emovox]]
- [[emotion-intensity-control]]
- [[relative-attributes-for-emotion-intensity]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[ser-perceptual-loss]]
- [[style-pretraining-for-evc]]
- [[emotional-speech-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
