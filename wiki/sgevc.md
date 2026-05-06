# SGEVC

**Summary**: SGEVC is a semi-supervised generative emotional voice conversion model that disentangles linguistic, speaker, and emotion variables. It is important for the emotion-speaker tradeoff because it explicitly models speaker identity and emotion as separate conditioning factors while reducing the need for labeled emotional data.

**Sources**:
- Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf

**Last updated**: 2026-05-06

---

## Task

SGEVC performs emotional voice conversion by changing the emotional state of speech while preserving linguistic information and speaker identity (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). The paper targets non-parallel EVC and limited emotion annotation, arguing that parallel emotional pairs and full emotion labels are costly in real applications (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Generative model

The method builds a semi-supervised generative model with separate variables for waveform, latent linguistic representation, emotion attribute, text condition, and speaker identity (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). The speaker identity variable is observed, while the emotion attribute is a categorical latent variable sampled with Gumbel-Softmax (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

The model uses a variational posterior over emotion and linguistic latent variables, and adds a supervised cross-entropy term when an observed emotion label is available (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). For unlabeled data, it modifies the lower bound with a thresholded KL term to avoid collapse of the emotion latent variable into the prior (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Architecture

SGEVC is based on VITS-style components: a transformer TTS encoder for the text-conditioned prior, a VC encoder conditioned on speaker and emotion attributes, normalizing flows between prior and posterior spaces, and a HiFi-GAN decoder for end-to-end waveform generation (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). Speaker identity is represented with a speaker lookup table, while emotion is extracted through a reference encoder followed by a Gumbel-Softmax layer and projection into a latent attribute embedding (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

During inference, source speaker and source emotion information condition the VC encoder and forward flow, while target speaker and target emotion information condition the decoder and inverse flow (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). This method record is important for [[speaker-emotion-tradeoff]] because the model has explicit slots for speaker and emotion, but the reported experiments focus on same-speaker emotion conversion rather than systematic speaker drift under emotion strength changes (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Data and evaluation

The experiments use the Mandarin subset of [[esd-dataset]], with neutral-to-happy, neutral-to-angry, neutral-to-sad, and neutral-to-surprise conversion for each speaker (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). The paper uses 330 training utterances and 20 test utterances per conversion pair, and shuffles training data to avoid parallel training batches (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

The paper evaluates emotion control with emotion classification accuracy under different supervision levels, and evaluates generated speech with MOS naturalness, emotion-similarity MOS, and MCD against StarGAN and PPG-based baselines (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). With the selected setting, SGEVC reports 84.1% emotion classification accuracy with 1% supervision and 91.3% with 10% supervision (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Tradeoff relevance

SGEVC is direct method evidence for [[speaker-disentanglement]] because it separates linguistic, speaker, and emotion spaces inside the generative model (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf). It is weaker as direct [[speaker-identity-evaluation-in-evc]] evidence because its main evaluation does not report SECS, sMOS, EER, or x-vector speaker similarity after emotion conversion (source: Zhu et al. - 2023 - Emotional Voice Conversion with Semi-Supervised Generative Modeling.pdf).

## Related pages

- [[semi-supervised-evc]]
- [[speaker-disentanglement]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[esd-dataset]]
- [[non-parallel-voice-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
- [[end-to-end-generative-evc]]
