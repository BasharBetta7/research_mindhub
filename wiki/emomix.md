# EmoMix

**Summary**: EmoMix is a diffusion-based emotional TTS model that mixes emotion conditions at run time. It is useful adjacent evidence for mixed-emotion synthesis and intensity control, but it is not a voice-conversion model.

**Sources**:
- Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Problem framing

EmoMix targets emotional text-to-speech synthesis with specified intensity or a mixture of emotions (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). The paper argues that many emotional TTS systems focus on a limited set of emotion types and struggle with intensity control (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

This paper is adjacent to [[emotional-speech-conversion]], but it is a TTS model rather than a voice-conversion model (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). It should be used mainly for [[mixed-emotion-synthesis]], [[diffusion-emotion-mixing]], and [[emotion-intensity-control]].

## Model

EmoMix builds on a GradTTS-style diffusion model and conditions synthesis on emotion embeddings from a pretrained speech emotion recognition model (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). It also uses a speaker embedding and a style reconstruction loss based on SER feature Gram matrices to encourage the generated speech to match reference emotional style (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

The key run-time mechanism is [[diffusion-emotion-mixing]], where noises predicted under different emotion conditions are combined during one diffusion sampling process (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). For intensity control, EmoMix mixes neutral and target-emotion conditions in varying proportions (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Data and setup

The SER model is trained on IEMOCAP, and EmoMix experiments use the English part of ESD with five emotions: sad, surprise, happy, neutral, and angry (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). The paper leaves angry as an unseen primary emotion in its experiments (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Results

For single primary emotion synthesis, EmoMix reports MOS 4.10 and SMOS 4.02 for seen emotions, compared with EmoDiff MOS 4.08 and SMOS 3.87 (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). For the unseen angry condition, EmoMix reports MOS 3.92 and SMOS 3.82 (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

The ablation study reports that replacing SER embeddings with discrete emotion labels reduces comparative similarity MOS by -0.16, and removing style reconstruction loss reduces it by -0.09 (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). The mixed-emotion experiment reports smaller quality degradation for EmoMix than MixedEmotion across weak, medium, and strong mixing settings (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf).

## Caution

The paper uses SER classifier probabilities to analyze mixed-emotion behavior, so the objective evidence partly depends on the same kind of emotion recognizer that may be imperfect for fine-grained perception (source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf). Claims about true human-perceived mixed emotion should therefore lean more on subjective evaluation than on classifier plots alone.

## Related pages

- [[mixed-emotion-synthesis]]
- [[diffusion-emotion-mixing]]
- [[emotion-intensity-control]]
- [[ser-perceptual-loss]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emotional-speech-conversion]]
