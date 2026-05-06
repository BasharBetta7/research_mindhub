# Hierarchical Emotion Rendering

**Summary**: Hierarchical Control of Emotion Rendering in Speech Synthesis proposes emotional TTS with controllable emotion distributions at utterance, word, and phoneme levels. It is strong evidence for fine-grained emotion-control design, but it is TTS rather than emotional voice conversion.

**Sources**:
- Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf

**Last updated**: 2026-05-06

---

## Problem

The paper targets emotional TTS where emotion rendering can be controlled at multiple linguistic levels rather than only at the whole-utterance level (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

It argues that utterance-level emotion control is insufficient because emotional expression can vary across phrases, words, and phonemes inside a single utterance (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Method

The paper proposes a diffusion-based emotional TTS framework with a [[hierarchical-emotion-distribution]] extractor and a Matcha-TTS-style conditional flow matching backbone (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The hierarchical ED extractor segments speech at the utterance, word, and phoneme levels, extracts acoustic or self-supervised speech features, and predicts emotion-intensity distributions for each segment level (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf). The paper explores OpenSMILE, WavLM, and HuBERT as feature sources for the emotion distribution extractor (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The model compares two classifier modules: a Speech Emotion Recognizer that predicts one of four emotions, and an Emotion Presence Recognizer that predicts presence or absence for each emotion independently (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

During TTS training, the hierarchical emotion distribution acts as a soft-label condition together with linguistic features and speaker embedding (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf). During inference, a user can modify the hierarchical emotion distribution to control emotion rendering at utterance, word, or phoneme level (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Results

The proposed EPR system reports better objective expressiveness and speaker-similarity values than the listed baselines in Table I, including WER 9.133, MCD 5.311 +- 0.128, pitch distortion 2.175 +- 0.106, WavLM SECS 0.871, and WeSpeaker SECS 0.511 (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

For utterance-level controllability, the proposed EPR system reports positive correlation 0.382, negative correlation 0.013, and score 0.369, outperforming the SVM-based HED baseline and proposed SER variant in Table II (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The MUSHRA results report that the proposed EPR system achieves naturalness 48.91 +- 2.360 and emotional similarity 59.41 +- 2.460, while ground truth and vocoder resynthesis are included as upper references for naturalness (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Caution

This source is important for [[hierarchical-emotion-control]] and [[emotion-intensity-control]], but it should not be cited as direct evidence for EVC speaker drift because it is an emotional TTS system rather than a voice-conversion system (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

The paper reports speaker-similarity metrics for synthesized speech, but that does not establish a speaker-emotion tradeoff curve because it does not sweep an EVC emotion-conversion strength against target-speaker preservation (source: Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf).

## Related pages

- [[hierarchical-emotion-control]]
- [[hierarchical-emotion-distribution]]
- [[emotion-intensity-control]]
- [[soft-label-guidance]]
- [[flow-matching-evc]]
- [[evaluation-metrics-for-voice-conversion]]
- [[speaker-emotion-tradeoff]]
