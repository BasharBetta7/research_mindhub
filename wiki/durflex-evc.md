# DurFlex-EVC

**Summary**: DurFlex-EVC is a duration-flexible emotional voice conversion framework that uses discrete speech units and a diffusion generator without text or forced alignment. It is central evidence for EVC systems that explicitly model duration and prosody.

**Sources**:
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf

**Last updated**: 2026-05-06

---

## Problem framing

DurFlex-EVC targets emotional voice conversion while preserving speaker identity and linguistic content (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). The authors argue that many EVC methods overlook rhythm because they support conversion with fixed durations or require text and alignment information (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Architecture

The framework uses HuBERT representations, a style autoencoder, a unit aligner, a duration predictor, a hierarchical stylize encoder, and a diffusion-based mel-spectrogram generator (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). The unit aligner predicts discrete unit sequences and durations, allowing duration control without text or external speech-text alignment (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

The style autoencoder removes source emotional style and applies target emotional style, while the hierarchical stylize encoder applies target style at both unit and frame levels (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Results

On ESD, DurFlex-EVC reports nMOS 3.70, sMOS 3.63, and eMOC 72.97, compared with Textless-EVC nMOS 3.61, sMOS 3.39, and eMOC 56.76 (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). In objective evaluation, DurFlex-EVC with 100 diffusion steps reports UTMOS 3.39, WER 20.75, ECA 88.64, EECS 0.85, and SECS 0.75 (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

DurFlex-EVC also reports better average pitch RMSE, energy RMSE, and DDUR than the compared EVC baselines (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf).

## Speaker identity relevance

DurFlex-EVC is important for [[speaker-identity-evaluation-in-evc]] because it reports speaker similarity and emotion metrics in the same evaluation, including sMOS, SECS, eMOC, ECA, and EECS (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). However, the paper does not sweep emotion intensity or conversion strength, so it does not by itself establish the shape of the [[speaker-emotion-tradeoff]].

## Caution

The method removes the need for text or alignment, but the experiments are still on ESD, an acted parallel emotional speech dataset (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf). Therefore, it is strong evidence for [[duration-flexible-evc]] on controlled EVC, but not direct evidence for [[in-the-wild-emotion-conversion]].

## Related pages

- [[duration-flexible-evc]]
- [[discrete-speech-units-for-evc]]
- [[emotional-speech-conversion]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[spectrum-prosody-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
