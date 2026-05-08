# Source Reliability Notes

**Summary**: Central notes for sources that should be cited with extra care because of metadata contradictions, task mismatch, proxy-evaluation limitations, or synthetic-data caveats. This page does not reject those sources; it records how they should and should not be used.

**Sources**:
- Didi+et+al.pdf
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf
- Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf
- Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf
- Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf
- Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf
- Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf

**Last updated**: 2026-05-07

---

## Purpose

This page centralizes cautions that are already distributed across the wiki. It helps prevent overclaiming when a paper is useful for architecture ideas, evaluation methods, or adjacent emotional speech generation but is weaker evidence for the core [[speaker-emotion-tradeoff]].

## Dataset Metadata Contradiction

[[seq2seq-cyclegan-evc]] is useful for architecture and metric design because it reports a hybrid Seq2Seq-plus-CycleGAN EVC system with speaker similarity, emotional similarity, MCD, F0 RMSE, SSIM, and MOS (source: Didi+et+al.pdf). However, the source describes ESD as containing more than 300 speakers, while the canonical ESD paper reports 20 speakers: 10 native English speakers and 10 native Chinese speakers (source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

Use the canonical 20-speaker ESD metadata from [[zhou-2022-evc-theory-esd]] and [[esd-dataset]] unless a separate dataset version is explicitly documented (source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). Treat Didi et al. as lower-confidence evidence for dataset details and quantitative benchmark claims, while preserving its architectural idea as a potentially useful pattern (source: Didi+et+al.pdf).

## Task Mismatch

Several emotional TTS papers are useful for intensity control, prompt control, evaluation design, or speaker-emotion disentanglement, but they should not be cited as direct EVC evidence for speaker drift under emotion conversion (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf; source: Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf; source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf; source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

[[tacotron]] and [[voicebox]] are backbone or general speech-generation references rather than emotional voice conversion evidence (source: Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf; source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf). Voicebox is especially easy to overcite for style transfer, but the paper notes that it cannot independently control voice, speaking style, emotion, and acoustic condition (source: Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf).

## Proxy Metrics

Automatic emotion metrics such as SER accuracy, classifier probability, and [[emotion2vec]] similarity are useful diagnostics, but they are not replacements for human perception (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). EmoVoice reports that emotion2vec has high system-level correlation with human ratings but much weaker sentence-level correlation, which is important when evaluating fine-grained emotional quality (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

This caution also applies when a system uses related representations for training, control, and evaluation, because the system may look strong under a proxy that matches its optimization target (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). See [[objective-speech-evaluation-metrics]] and [[evaluation-metrics-for-voice-conversion]] for the metric taxonomy.

## Synthetic Data Caveat

[[emovoice-db]] is synthetic emotional speech generated with GPT-4o-audio and then filtered or selected for training (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf). It is useful for scaling natural-language emotion control, but claims that it covers the full distribution of real human emotional speech should remain marked as needing verification unless supported by independent human-data comparisons (source: Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf).

## Related pages

- [[seq2seq-cyclegan-evc]]
- [[esd-dataset]]
- [[zhou-2022-evc-theory-esd]]
- [[evaluation-metrics-for-voice-conversion]]
- [[objective-speech-evaluation-metrics]]
- [[speaker-emotion-tradeoff]]
- [[emovoice]]
- [[emovoice-db]]
- [[synthetic-emotional-speech-data]]
- [[voicebox]]
- [[tacotron]]

