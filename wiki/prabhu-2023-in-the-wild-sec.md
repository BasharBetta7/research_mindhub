# Prabhu 2023 In The Wild SEC

**Summary**: Prabhu et al. 2023 proposes in-the-wild speech emotion conversion using disentangled self-supervised representations and HiFi-GAN resynthesis. It is direct evidence for continuous arousal-based SEC/EVC on non-parallel naturalistic data.

**Sources**:
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf

**Last updated**: 2026-05-06

---

## Problem

The paper defines speech emotion conversion as converting the expressed emotion of a spoken utterance to a target emotion while preserving lexical information and speaker identity (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

The paper focuses on in-the-wild emotion conversion where parallel source-target emotional utterances are unavailable, so lexical, speaker, and emotion information must be disentangled from non-parallel speech (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Method

The method uses [[ssl-disentanglement-for-sec]] to separate lexical, speaker, and emotion factors before resynthesis (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

The lexical encoder uses pretrained HuBERT representations converted into discrete units with k-means clustering, motivated by prior work showing that these units are related to phoneme content (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

The speaker encoder uses a pretrained WavLM speaker verification model to produce a 512-dimensional global speaker representation (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

The emotion encoder maps the utterance-level arousal scalar into a 128-dimensional emotion representation, making the method a continuous [[arousal-based-emotion-control]] system rather than a categorical-label conversion system (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

The decoder is a modified HiFi-GAN trained to resynthesize speech from the concatenated lexical, speaker, and emotion representations (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Data and evaluation

The experiments use MSP-Podcast v1.10, an in-the-wild podcast dataset with about 166 hours of audio annotated for arousal, valence, and dominance (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

The paper uses only arousal annotations, which are on a 1 to 7 scale and are concentrated around the middle of the scale (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

Emotion-conversion capability is evaluated with mean-squared and mean-absolute errors between target arousal and a pretrained SER model's prediction on resynthesized speech (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf). Naturalness is evaluated with WVMOS, a wav2vec-based objective speech quality proxy trained on Voice Conversion Challenge MOS data (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Results

Adding lexical, speaker, emotion, and SER-loss conditioning improves naturalness and arousal conversion in the reported model comparison (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf). The full model reports WVMOS 3.26, mean-squared arousal error 0.0843, and mean-absolute arousal error 0.2442, with statistically significant improvements over the preceding version without SER loss (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

The paper reports better conversion for mid-scale arousal values than for extreme arousal values 1 and 7 (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

Pitch-contour analysis shows that synthesized high-arousal speech has higher mean and variability of pitch than the ground-truth and low-arousal synthesized samples (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Caution

This paper is direct evidence for in-the-wild arousal conversion, but the speaker-preservation side is weaker than the emotion side because the reported evaluation emphasizes SER arousal error and WVMOS rather than explicit speaker-similarity metrics (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

Its emotion evaluation relies on a pretrained SER model, so the results should be read with the proxy-metric caution used for [[ser-perceptual-loss]] and [[evaluation-metrics-for-voice-conversion]] (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Related pages

- [[in-the-wild-emotion-conversion]]
- [[ssl-disentanglement-for-sec]]
- [[arousal-based-emotion-control]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[ser-perceptual-loss]]
- [[evaluation-metrics-for-voice-conversion]]
