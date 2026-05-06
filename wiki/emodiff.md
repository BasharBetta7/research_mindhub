# EmoDiff

**Summary**: EmoDiff is a diffusion-based emotional TTS model that controls emotion intensity with soft-label classifier guidance. It is directly useful for intensity-control concepts, but it is TTS rather than emotional voice conversion.

**Sources**:
- Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf

**Last updated**: 2026-05-06

---

## Problem

EmoDiff targets intensity-controllable emotional text-to-speech, where the model should synthesize a target emotion at a chosen strength while preserving voice quality (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

The paper argues that many emotional TTS systems use categorical emotion labels and therefore cannot directly control emotion intensity (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). It also criticizes external intensity-estimation pipelines such as relative-attribute ranking because they can add a separate optimization stage and bias the training signal (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

## Method

EmoDiff trains an emotion-unconditional Grad-TTS acoustic model and a separate emotion classifier that operates on noisy mel-spectrogram states during diffusion sampling (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

The main mechanism is [[soft-label-guidance]], where the target emotion label is replaced by a soft label with target-emotion weight alpha and neutral-emotion weight 1-alpha (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). The paper interprets alpha in the range 0 to 1 as the target emotion intensity (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

The same guidance mechanism can extend beyond single-emotion intensity control to mixed-emotion control by assigning weights to multiple emotion labels (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

## Data and setup

The experiments use the English part of ESD, which contains 10 speakers and five emotion categories: angry, happy, sad, surprise, and neutral (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). Each speaker has 350 parallel utterances per emotion category, for about 1.2 hours of speech per speaker (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

The paper frames the experiments as single-speaker emotional TTS: the unconditional Grad-TTS acoustic model is trained on all 10 English ESD speakers, while the classifier is trained on female speaker ID 0015 (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). HiFi-GAN trained on all English ESD speakers is used as the vocoder (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

## Results

For full-intensity emotional synthesis, EmoDiff reports MOS 4.13 +- 0.10 and MCD 5.98, compared with MixedEmotion MOS 3.43 +- 0.12 and MCD 6.62 (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). The hard-label Grad-TTS baseline reports MOS 4.16 +- 0.10 and MCD 5.75 but does not provide intensity controllability (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

For intensity control, the paper evaluates target-emotion classifier probability while sweeping alpha from 0.0 to 1.0 (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf). EmoDiff covers a larger probability range and shows lower error range than the MixedEmotion baseline in the reported classifier-probability plots (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

## Caution

EmoDiff is valuable for [[emotion-intensity-control]], [[mixed-emotion-synthesis]], and [[diffusion-based-emotion-conversion]] background, but it is not direct EVC evidence because it synthesizes speech from text rather than converting a source utterance (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

Its intensity-control evaluation depends partly on a trained emotion classifier, so classifier probability should be treated as a proxy for perceived emotion intensity rather than a full replacement for human listening tests (source: Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf).

## Related pages

- [[soft-label-guidance]]
- [[emotion-intensity-control]]
- [[mixed-emotion-synthesis]]
- [[diffusion-based-emotion-conversion]]
- [[emomix]]
- [[relative-attributes-for-emotion-intensity]]
- [[ser-perceptual-loss]]
- [[evaluation-metrics-for-voice-conversion]]
