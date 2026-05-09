# Wiki Log

**Summary**: Append-only record of wiki operations.

**Sources**: Personal wiki metadata.

**Last updated**: 2026-05-08

---

**Timestamp**: [08-05-2026 14:38]

- Ingested `Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf`.
- Created source summary page [[promptevc]].
- Updated existing pages: [[natural-language-emotion-control]], [[freestyle-emotion-prompting]], [[emotion2vec]], [[emotion-intensity-control]], [[speaker-identity-evaluation-in-evc]], and [[index]].
- Updated `../sources.bib` with a BibTeX entry for PromptEVC.

**Timestamp**: [07-05-2026 21:35]

- Ran a second critique pass on expanded `exp/MODEL_inferred_intensity` outputs.
- Created `exp_wiki/model-inferred-intensity-gap-analysis.md` covering ESD SSST/DSST, CREMA-D pretrained and finetuned conditions, listening-study evidence, baseline gaps, metric gaps, and recommended next analyses.
- Updated `exp_wiki/index.md` and [[index]] with the new experiment critique page.

**Timestamp**: [07-05-2026 18:17]

- Applied wiki audit cleanup.
- Created [[objective-speech-evaluation-metrics]] as a compact glossary for recurring speech quality, content, speaker, emotion, and prosody metrics.
- Created [[source-reliability-notes]] to centralize the Didi/ESD metadata contradiction, task-mismatch cautions, proxy-metric cautions, and synthetic-data caveats.
- Updated [[evaluation-metrics-for-voice-conversion]], [[speaker-similarity-metrics]], [[seq2seq-cyclegan-evc]], [[esd-dataset]], and [[index]] with links to the new pages.

**Timestamp**: [07-05-2026 14:06]

- Updated `exp_wiki/model-inferred-intensity-alpha-critique.md` to embed and analyze experiment plots from `exp/MODEL_inferred_intensity`.
- Added visual evidence sections for the alpha sweep, speaker-cosine drift, per-emotion alpha behavior, epoch sweep, and style-space PCA.

**Timestamp**: [07-05-2026 13:45]

- Ran critique on `exp/MODEL_inferred_intensity`.
- Created `exp_wiki/index.md`.
- Created `exp_wiki/model-inferred-intensity-alpha-critique.md` with analysis of the alpha sweep, epoch sweep, emotion-specific failures, speaker-specific drift, and methodology cautions.
- Updated [[index]] with links to the experiment critique pages.

**Timestamp**: [06-05-2026 22:37]

- Ingested `Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf`.
- Ingested `Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf`.
- Ingested `Didi+et+al.pdf`.
- Created source summary pages [[zhou-2022-evc-theory-esd]], [[sgevc]], and [[seq2seq-cyclegan-evc]].
- Created concept pages [[esd-dataset]], [[emotional-speech-databases]], [[semi-supervised-evc]], [[end-to-end-generative-evc]], and [[seq2seq-cyclegan-refinement]].
- Updated existing pages with extra emphasis on source methods and the emotion-speaker tradeoff: [[speaker-emotion-tradeoff]], [[speaker-identity-evaluation-in-evc]], [[speaker-disentanglement]], [[evaluation-metrics-for-voice-conversion]], [[f0-pitch-contour-in-voice-conversion]], [[sequence-to-sequence-emotional-voice-conversion]], [[cyclegan-evc]], [[parallel-emotional-speech-data]], [[non-parallel-voice-conversion]], [[emotional-speech-conversion]], and [[index]].
- Updated `../sources.bib` with entries for the newly ingested raw PDFs.

**Timestamp**: [06-05-2026 22:22]

- Ingested `Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf`; the PDF title is DiffEVC and the wiki records the filename/title mismatch.
- Ingested `Dutta and Ganapathy - 2024 - Zero Shot Audio to Audio Emotion Transfer With Speaker Disentanglement.pdf`.
- Ingested `Kreuk et al. - 2022 - Textless Speech Emotion Conversion using Discrete and Decomposed Representations.pdf`.
- Created source summary pages [[diffevc]], [[zest]], and [[textless-speech-emotion-conversion]].
- Created concept pages [[expressive-guidance]], [[mutual-information-disentanglement]], [[zero-shot-audio-to-audio-emotion-transfer]], and [[textless-emotion-conversion]].
- Updated existing pages: [[speaker-emotion-tradeoff]], [[speaker-identity-evaluation-in-evc]], [[emotion-intensity-control]], [[f0-pitch-contour-in-voice-conversion]], [[discrete-speech-units-for-evc]], [[diffusion-based-emotion-conversion]], [[evaluation-metrics-for-voice-conversion]], [[speaker-disentanglement]], [[ssl-disentanglement-for-sec]], [[in-the-wild-emotion-conversion]], and [[index]].
- Updated `../sources.bib` with entries for the newly ingested raw PDFs.

**Timestamp**: [06-05-2026 21:47]

- Added concept page [[f0-pitch-contour-in-voice-conversion]] from a question-answer synthesis about why F0/pitch contour extraction matters in voice conversion.
- Updated existing pages: [[f0-consistency-loss]], [[spectrum-prosody-conversion]], and [[index]].

**Timestamp**: [06-05-2026 21:17]

- Ingested `Prabhu et al. - 2023 - In-the-wild Speech Emotion Conversion Using Disentangled Self-Supervised Representations and Neural.pdf`.
- Ingested `Qi et al. - 2024 - Towards Realistic Emotional Voice Conversion using Controllable Emotional Intensity.pdf`.
- Ingested `Le et al. - 2023 - Voicebox Text-Guided Multilingual Universal Speech Generation at Scale.pdf`.
- Ingested `Wang et al. - 2017 - Tacotron Towards End-to-End Speech Synthesis.pdf`.
- Created source summary pages [[prabhu-2023-in-the-wild-sec]], [[einet]], [[voicebox]], and [[tacotron]].
- Created concept pages: [[ssl-disentanglement-for-sec]], [[vad-based-emotion-intensity]], [[text-guided-speech-infilling]], and [[seq2seq-tts]].
- Updated existing pages: [[in-the-wild-emotion-conversion]], [[arousal-based-emotion-control]], [[emotion-intensity-control]], [[speaker-identity-evaluation-in-evc]], [[speaker-emotion-tradeoff]], [[flow-matching-evc]], [[sequence-to-sequence-emotional-voice-conversion]], [[evaluation-metrics-for-voice-conversion]], [[ser-perceptual-loss]], [[speaker-disentanglement]], and [[index]].
- Updated `../sources.bib` with entries for the newly ingested raw PDFs.

**Timestamp**: [06-05-2026 21:12]

- Ingested `Zhao et al. - 2024 - Temporal-Frequency State Space Duality An Efficient Paradigm for Speech Emotion Recognition.pdf`.
- Created source summary page [[tf-mamba-ser]].
- Created concept page [[temporal-frequency-ser]].
- Updated existing pages: [[ser-perceptual-loss]], [[deep-emotional-features]], [[emotion2vec]], [[evaluation-metrics-for-voice-conversion]], [[speaker-emotion-tradeoff]], and [[index]].
- Updated `../sources.bib` with a BibTeX entry for TF-Mamba.

**Timestamp**: [06-05-2026 16:42]

- Ingested `Guo et al. - 2023 - EmoDiff Intensity Controllable Emotional Text-to-Speech with Soft-Label Guidance.pdf`.
- Ingested `Inoue et al. - 2025 - Hierarchical Control of Emotion Rendering in Speech Synthesis.pdf`.
- Ingested `Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf`.
- Ingested `Kim et al. - 2020 - Glow-TTS A Generative Flow for Text-to-Speech via Monotonic Alignment Search.pdf`.
- Created source summary pages [[emodiff]], [[hierarchical-emotion-rendering]], [[e3-tts]], and [[glow-tts]].
- Created concept pages: [[soft-label-guidance]], [[hierarchical-emotion-control]], [[hierarchical-emotion-distribution]], [[end-to-end-diffusion-tts]], [[flow-based-tts]], and [[monotonic-alignment-search]].
- Updated existing pages: [[emotion-intensity-control]], [[mixed-emotion-synthesis]], [[diffusion-based-emotion-conversion]], [[flow-matching-evc]], [[evaluation-metrics-for-voice-conversion]], [[speaker-emotion-tradeoff]], [[speaker-identity-evaluation-in-evc]], and [[index]].
- Updated `../sources.bib` with entries for EmoDiff, Hierarchical Control of Emotion Rendering, and Glow-TTS.

**Timestamp**: [06-05-2026 16:06]

- Applied wiki audit fixes.
- Added missing cited sources to [[autovc]], [[emotion-intensity-and-control]], [[speaker-disentanglement]], and [[yang-2022-seq2seq-evc-overview]].
- Created concept pages [[emotion2vec]], [[speaker-similarity-metrics]], and [[self-supervised-emotion-disentanglement]].
- Updated existing pages: [[evaluation-metrics-for-voice-conversion]], [[ser-perceptual-loss]], [[speaker-identity-evaluation-in-evc]], [[diemo-tts]], [[cross-speaker-emotion-transfer]], [[speaker-emotion-tradeoff]], and [[index]].
- Updated `../sources.bib` with a missing entry for `Gao et al. - 2023 - E3 TTS Easy End-to-End Diffusion-based Text to Speech.pdf`.

**Timestamp**: [06-05-2026 15:52]

- Ingested `Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf`.
- Ingested `Cho et al. - 2025 - DiEmo-TTS Disentangled Emotion Representations via Self-Supervised Distillation for Cross-Speaker E.pdf`.
- Ingested `Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf`.
- Created source summary pages [[daisy-tts]], [[diemo-tts]], and [[clapfm-evc]].
- Created concept pages: [[prosody-embedding-decomposition]], [[cross-speaker-emotion-transfer]], [[natural-language-emotion-control]], [[evc-clap]], [[adaptive-intensity-gate]], and [[flow-matching-evc]].
- Updated existing pages: [[emotion-intensity-control]], [[freestyle-emotion-prompting]], [[mixed-emotion-synthesis]], [[speaker-identity-evaluation-in-evc]], [[diffusion-based-emotion-conversion]], [[evaluation-metrics-for-voice-conversion]], [[speaker-emotion-tradeoff]], [[emotional-speech-conversion]], [[spectrum-prosody-conversion]], [[pflow-vc]], [[pitch-conditioned-flow-matching]], and [[index]].
- Updated `../sources.bib` with entries for the newly added raw PDFs.

**Timestamp**: [06-05-2026 15:41]

- Ingested `Yang et al. - 2022 - An Overview & Analysis of Sequence-to-Sequence Emotional Voice Conversion.pdf`.
- Created source summary page [[yang-2022-seq2seq-evc-overview]].
- Created concept page [[parallel-emotional-speech-data]].
- Updated existing pages: [[sequence-to-sequence-emotional-voice-conversion]], [[evaluation-metrics-for-voice-conversion]], [[emotional-speech-conversion]], [[duration-flexible-evc]], [[spectrum-prosody-conversion]], [[speaker-emotion-tradeoff]], and [[index]].

**Timestamp**: [06-05-2026 15:32]

- Added `../sources.bib` with BibTeX entries for all source PDFs currently stored in `research_mindhub/raw/`.
- Updated [[index]] with a pointer to the bibliography file.

**Timestamp**: [06-05-2026 15:03]

- Audited the wiki for speaker-emotion tradeoff coverage after question-answer synthesis.
- Created concept page [[speaker-identity-evaluation-in-evc]].
- Updated existing pages: [[speaker-emotion-tradeoff]], [[evaluation-metrics-for-voice-conversion]], [[durflex-evc]], [[pflow-vc]], [[emoconv-diff]], and [[index]].

**Timestamp**: [06-05-2026 14:26]

- Ingested `Oh et al. - 2025 - DurFlex-EVC Duration-Flexible Emotional Voice Conversion Leveraging Discrete Representations withou.pdf`.
- Ingested `Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf`.
- Ingested `Zuo et al. - 2025 - Enhancing Expressive Voice Conversion with Discrete Pitch-Conditioned Flow Matching Model.pdf`.
- Created source summary pages [[durflex-evc]], [[deepest]], and [[pflow-vc]].
- Created concept pages: [[duration-flexible-evc]], [[discrete-speech-units-for-evc]], [[deep-emotional-features]], [[seen-and-unseen-emotion-transfer]], [[pitch-conditioned-flow-matching]], and [[time-varying-timbre-tokens]].
- Updated existing pages: [[emotional-speech-conversion]], [[emotion-intensity-control]], [[evaluation-metrics-for-voice-conversion]], [[spectrum-prosody-conversion]], [[speaker-emotion-tradeoff]], [[ser-perceptual-loss]], [[non-parallel-voice-conversion]], [[sequence-to-sequence-emotional-voice-conversion]], and [[index]].

**Timestamp**: [06-05-2026 14:16]

- Ingested `Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf`.
- Ingested `Tang et al. - 2023 - EmoMix Emotion Mixing via Diffusion Models for Emotional Speech Synthesis.pdf`.
- Created source summary pages [[emoconv-diff]] and [[emomix]].
- Created concept pages: [[diffusion-based-emotion-conversion]], [[in-the-wild-emotion-conversion]], [[arousal-based-emotion-control]], [[mixed-emotion-synthesis]], and [[diffusion-emotion-mixing]].
- Updated existing pages: [[emotional-speech-conversion]], [[emotion-intensity-control]], [[evaluation-metrics-for-voice-conversion]], [[spectrum-prosody-conversion]], [[ser-perceptual-loss]], [[speaker-emotion-tradeoff]], and [[index]].

**Timestamp**: [06-05-2026 14:11]

- Ingested `Yang et al. - 2025 - EmoVoice LLM-based Emotional Text-To-Speech Model with Freestyle Text Prompting.pdf`.
- Created source summary page [[emovoice]].
- Created concept pages: [[llm-based-emotional-tts]], [[freestyle-emotion-prompting]], [[emovoice-db]], [[phoneme-boosted-tts]], and [[synthetic-emotional-speech-data]].
- Updated existing pages: [[emotional-speech-conversion]], [[emotion-intensity-control]], [[evaluation-metrics-for-voice-conversion]], [[ser-perceptual-loss]], [[speaker-emotion-tradeoff]], and [[index]].

**Timestamp**: [06-05-2026 00:59]

- Created concept page [[speaker-emotion-tradeoff]] from a wiki question-answer synthesis.
- Updated [[index]] and cross-linked related pages: [[emo-stargan]], [[emotion-preserving-voice-conversion]], [[evaluation-metrics-for-voice-conversion]], [[speaker-disentanglement]], and [[adversarial-source-classifier-loss]].

**Timestamp**: [06-05-2026 00:44]

- Ingested `Zhou et al. - 2020 - Transforming Spectrum and Prosody for Emotional Voice Conversion with Non-Parallel Training Data.pdf`.
- Created source summary page [[transforming-spectrum-and-prosody-for-evc]].
- Created concept pages: [[cyclegan-evc]], [[cwt-f0-modelling]], [[spectrum-prosody-conversion]], and [[separate-vs-joint-prosody-training]].
- Updated existing pages: [[emotional-speech-conversion]], [[non-parallel-voice-conversion]], [[f0-consistency-loss]], [[emotion-intensity-control]], [[sequence-to-sequence-emotional-voice-conversion]], [[evaluation-metrics-for-voice-conversion]], and [[index]].

**Timestamp**: [06-05-2026 00:40]

- Ingested `Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf`.
- Created source summary page [[emotion-intensity-and-control]].
- Created concept pages: [[emovox]], [[emotion-intensity-control]], [[relative-attributes-for-emotion-intensity]], [[sequence-to-sequence-emotional-voice-conversion]], [[ser-perceptual-loss]], and [[style-pretraining-for-evc]].
- Updated existing pages: [[emotional-speech-conversion]], [[emotion-preserving-voice-conversion]], [[evaluation-metrics-for-voice-conversion]], [[f0-consistency-loss]], and [[index]].

**Timestamp**: [06-05-2026 00:37]

- Ingested `Ghosh et al. - 2023 - Emo-StarGAN A Semi-Supervised Any-to-Many Non-Parallel Emotion-Preserving Voice Conversion.pdf`.
- Ingested `Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf`.
- Created source summary pages [[emo-stargan]] and [[autovc]].
- Created concept pages: [[zero-shot-voice-conversion]], [[autoencoder-voice-conversion]], [[information-bottleneck-for-voice-conversion]], [[speaker-disentanglement]], [[speech-anonymisation]], [[emotion-preserving-voice-conversion]], [[emotion-embedding-loss]], [[emotion-aware-acoustic-feature-loss]], and [[emotion-classifier-loss]].
- Updated existing pages: [[voice-conversion]], [[non-parallel-voice-conversion]], [[many-to-many-voice-conversion]], [[starganv2-vc]], [[emotional-speech-conversion]], [[evaluation-metrics-for-voice-conversion]], and [[index]].

**Timestamp**: [06-05-2026 00:37]

- Ingested `Li et al. - 2021 - StarGANv2-VC A Diverse, Unsupervised, Non-parallel Framework for Natural-Sounding Voice Conversion.pdf`.
- Created source summary page [[starganv2-vc]].
- Created concept pages: [[voice-conversion]], [[non-parallel-voice-conversion]], [[many-to-many-voice-conversion]], [[stargan-v2]], [[style-encoder]], [[mapping-network]], [[adversarial-source-classifier-loss]], [[f0-consistency-loss]], [[asr-speech-consistency-loss]], [[evaluation-metrics-for-voice-conversion]], and [[emotional-speech-conversion]].
- Updated [[index]] with the new pages and one-line descriptions.
