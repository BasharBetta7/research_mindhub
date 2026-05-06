# TF-Mamba SER

**Summary**: TF-Mamba is a speech emotion recognition model that combines temporal-domain and frequency-domain state-space modeling. It is useful as SER representation and proxy-evaluation background, not as direct evidence for emotional voice conversion.

**Sources**:
- Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf

**Last updated**: 2026-05-06

---

## Problem

TF-Mamba targets speech emotion recognition, where the goal is to identify emotional states from vocal cues (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The paper argues that existing SER methods focus too heavily on temporal-domain analysis and underuse frequency-domain envelope structure, which can expose tone, timbre, pitch, and intonation cues relevant to emotion recognition (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## Method

The model first extracts speech embeddings with WavLM-Large and refines them with a self-attention encoder (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

Its core component is a temporal-frequency Mamba block that models temporal-aware and frequency-aware emotional features with a bi-domain State Space Duality structure (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf). This places TF-Mamba under [[temporal-frequency-ser]].

The temporal branch uses a one-dimensional convolution and SiLU activation to capture short-term temporal dependencies and subtle emotional variations across time steps (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The frequency branch applies FFT, an adaptive low-pass filter, and inverse FFT to emphasize frequency-domain emotional structure while reducing high-frequency noise (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The paper also proposes Complex Metric-Distance Triplet loss, which uses complex-domain vector similarity after FFT to cluster same-emotion samples and separate different-emotion samples (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## Data and metrics

The experiments use IEMOCAP and MELD as SER benchmarks (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf). IEMOCAP is evaluated with weighted accuracy and unweighted accuracy, while MELD is evaluated with weighted F1 (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The IEMOCAP setup uses four emotion groups: happy and excited, angry, sad, and neutral (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf). The MELD setup uses seven emotions: anger, disgust, fear, joy, neutral, sadness, and surprise (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## Results

TF-Mamba reports 75.3% weighted accuracy and 75.7% unweighted accuracy on IEMOCAP, and 48.5% weighted F1 on MELD (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The ablation table shows performance rising from the baseline to the full model: on IEMOCAP, weighted accuracy improves from 64.5% to 75.3%, and unweighted accuracy improves from 65.3% to 75.7% (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf). On MELD, weighted F1 improves from 40.3% to 48.5% across the same ablation path (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

The paper reports that TF-Mamba reduces parameters by 1.81 times and latency by 1.87 times compared with ShiftFormer, while improving SER performance (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## Relevance to this wiki

TF-Mamba is relevant to [[ser-perceptual-loss]], [[deep-emotional-features]], and [[evaluation-metrics-for-voice-conversion]] because emotional speech generation papers often use SER models as conditioning, training losses, or evaluation proxies (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

TF-Mamba is not direct evidence for [[speaker-emotion-tradeoff]] because it does not synthesize or convert speech, and it does not measure speaker identity preservation under emotional conversion (source: Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf).

## Related pages

- [[temporal-frequency-ser]]
- [[ser-perceptual-loss]]
- [[deep-emotional-features]]
- [[evaluation-metrics-for-voice-conversion]]
- [[emotion2vec]]
- [[speaker-emotion-tradeoff]]
