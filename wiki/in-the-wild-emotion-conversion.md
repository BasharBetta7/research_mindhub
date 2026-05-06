# In-The-Wild Emotion Conversion

**Summary**: In-the-wild emotion conversion studies emotional speech conversion on naturalistic, non-parallel data with real-world variability. The wiki now covers both SSL-resynthesis SEC and diffusion-based SEC in this setting.

**Sources**:
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf
- Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf
- Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf

**Last updated**: 2026-05-06

---

## Definition

In-the-wild emotion conversion converts emotional attributes in speech collected under naturalistic conditions rather than controlled acted recordings (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). Both [[prabhu-2023-in-the-wild-sec]] and [[emoconv-diff]] focus on MSP-Podcast v1.10 as the in-the-wild data source (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf; source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

## Motivation

The paper argues that models trained on acted-out speech can be sensitive to real-world variability such as acoustic noise, speaker variability, subtle intonation, and vocal bursts (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). It also argues that acted datasets can encourage stereotypical emotion portrayals (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

[[prabhu-2023-in-the-wild-sec]] motivates the same setting from the scarcity of parallel acted emotional data and the need to disentangle lexical, speaker, and emotion information in non-parallel data (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Dataset implications

MSP-Podcast v1.10 is described as about 238 hours of audio from more than 1400 speakers with variable durations and naturalistic emotional expressions (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). Because there are no parallel references, evaluation cannot rely on intrusive metrics requiring paired target speech (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

Prabhu et al. 2023 describes MSP-Podcast v1.10 as about 166 hours of podcast audio annotated with arousal, valence, and dominance, and uses only arousal for conversion (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf). The duration mismatch between the two descriptions should be treated as source-version or preprocessing dependent unless verified (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf; source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

[[diffevc]] also uses MSP-Podcast, training on v1.10 and evaluating on v1.11 as an in-the-wild any-to-any EVC setting with unseen speakers and reference emotions (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). This adds a categorical-emotion counterpart to the arousal-focused in-the-wild SEC sources already in the wiki (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Caution

In-the-wild data increases ecological validity, but it makes causal interpretation harder because emotion, speaker, channel, and context can be entangled (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). EmoConv-Diff addresses this with separate encoders, but speaker-emotion disentanglement should still be evaluated directly.

[[ssl-disentanglement-for-sec]] addresses this issue by using HuBERT for lexical content, WavLM for speaker identity, and an arousal embedding for emotion, but explicit speaker-similarity evaluation is still needed to confirm identity preservation (source: Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf).

## Related pages

- [[emoconv-diff]]
- [[prabhu-2023-in-the-wild-sec]]
- [[ssl-disentanglement-for-sec]]
- [[diffusion-based-emotion-conversion]]
- [[arousal-based-emotion-control]]
- [[non-parallel-voice-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
- [[diffevc]]
- [[expressive-guidance]]
- [[mutual-information-disentanglement]]
