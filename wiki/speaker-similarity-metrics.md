# Speaker Similarity Metrics

**Summary**: Speaker similarity metrics measure whether converted or synthesized speech sounds like the intended speaker. The wiki uses EER, speaker classification accuracy, sMOS, SECS, and SMOS as related but non-identical speaker-side measures.

**Sources**:
- Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf
- Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf
- Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf
- Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf
- Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf

**Last updated**: 2026-05-07

---

## Definition

Speaker similarity metrics evaluate speaker preservation, speaker conversion, or speaker anonymisation depending on the task (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf; source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf). They are the speaker-side counterpart to emotion metrics in the [[speaker-emotion-tradeoff]].

## Metrics In The Wiki

[[emo-stargan]] uses EER to evaluate anonymisation while measuring emotion preservation (source: Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf). [[starganv2-vc]] reports speaker classification accuracy as an objective speaker-similarity proxy (source: Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf).

[[durflex-evc]] reports subjective sMOS and objective SECS, while [[pflow-vc]] reports speaker embedding cosine similarity and SMOS (source: Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf; source: Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf). [[diemo-tts]] reports sMOS and SECS for cross-speaker emotional TTS, which is adjacent evidence rather than EVC evidence (source: Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf).

[[objective-speech-evaluation-metrics]] gives short definitions for EER, SECS, x-vector/d-vector cosine similarity, sMOS, SMOS, and related objective metrics used across the wiki.

## Caution

[[clapfm-evc]] reports strong emotion-similarity and quality metrics but does not include explicit speaker-similarity metrics in its main comparison table (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). This makes it weaker evidence for speaker preservation than systems that report SECS, sMOS, SMOS, EER, or speaker classification accuracy (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Related pages

- [[speaker-identity-evaluation-in-evc]]
- [[speaker-emotion-tradeoff]]
- [[evaluation-metrics-for-voice-conversion]]
- [[objective-speech-evaluation-metrics]]
- [[emo-stargan]]
- [[starganv2-vc]]
- [[durflex-evc]]
- [[pflow-vc]]
- [[diemo-tts]]
- [[clapfm-evc]]
