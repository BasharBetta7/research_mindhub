# ClapFM-EVC

**Summary**: ClapFM-EVC is an any-to-one emotional voice conversion framework with reference-speech or natural-language-prompt control and adjustable emotion intensity. It is directly relevant to flexible EVC control, but its reported main evaluation emphasizes quality and emotion similarity more than speaker-identity drift.

**Sources**:
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf

**Last updated**: 2026-05-06

---

## Problem

ClapFM-EVC targets high-fidelity [[emotional-speech-conversion]] with flexible and interpretable control (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). The paper argues that existing EVC systems often rely on reference speech or categorical labels, which limits emotional diversity, interpretability, and user control (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Architecture

ClapFM-EVC consists of [[evc-clap]], AdaFM-VC, a pretrained ASR model, and a pretrained vocoder (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). EVC-CLAP aligns emotional information across audio and text modalities using speech, categorical emotion labels, and natural-language prompts (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

AdaFM-VC uses a FuEncoder with an [[adaptive-intensity-gate]] to fuse PPG content features with emotion embeddings while controlling emotion intensity (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). The decoder is a [[flow-matching-evc]] component that reconstructs target mel-spectrograms with conditional flow matching (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Control Modes

During inference, ClapFM-EVC can obtain target emotional embeddings from reference speech, from a natural-language emotional prompt, or by retrieving reference speech with a natural-language prompt and then extracting target emotion elements from the retrieved speech (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). This makes it directly relevant to [[natural-language-emotion-control]] and [[freestyle-emotion-prompting]].

## Evaluation

The paper evaluates speech quality with MCD, RMSE, CER, UTMOS, and nMOS, and evaluates emotion similarity with EECS and eMOS (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). In reference-speech EVC, ClapFM-EVC reports MCD 5.83, RMSE 10.91, CER 6.76, UTMOS 3.68, nMOS 4.09, EECS 0.82, and eMOS 3.85, outperforming StarGAN-EVC, Seq2seq-EVC, and MixEmo on the reported table (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

For prompt-driven EVC, an ABX preference test reports that 57.4% of participants had no preference between reference-driven and prompt-driven emotion similarity, while 19.1% favored prompt-driven conversion (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). The paper also reports that removing categorical emotion labels, replacing symKL with KL, or removing AIG harms emotion similarity or speech quality in ablations (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Speaker-Emotion Relevance

ClapFM-EVC states the EVC goal as changing the emotional state while preserving content and speaker identity (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). However, the reported main tables focus on speech quality and emotion similarity rather than speaker similarity metrics such as SECS, sMOS, or EER, so it does not close the current [[speaker-emotion-tradeoff]] evidence gap (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Related pages

- [[evc-clap]]
- [[natural-language-emotion-control]]
- [[adaptive-intensity-gate]]
- [[flow-matching-evc]]
- [[emotion-intensity-control]]
- [[freestyle-emotion-prompting]]
- [[evaluation-metrics-for-voice-conversion]]
- [[speaker-emotion-tradeoff]]

