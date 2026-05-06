# Deep Emotional Features

**Summary**: Deep emotional features are latent emotion descriptors extracted by a speech emotion recognizer. DeepEST uses them as continuous style conditions for seen and unseen emotional style transfer.

**Sources**:
- Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf

**Last updated**: 2026-05-06

---

## Definition

Deep emotional features are utterance-level embeddings extracted from a pretrained SER model to describe emotional prosody in a continuous space (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). [[deepest]] uses these features as a condition for emotional style transfer (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf).

## Motivation

The DeepEST paper argues that emotional prosody is not well represented by simple one-hot emotion labels because it spreads over a continuum (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). The authors visualize SER features with t-SNE and show emotion-group structure, motivating their use as style embeddings (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf).

## Caution

Deep emotional features inherit the strengths and weaknesses of the SER model that produces them (source: Zhou et al. - 2021 - Seen and Unseen emotional style transfer for voice conversion with a new emotional speech dataset.pdf). The paper notes that weaker SER performance for happy affects emotion similarity results, so these features are useful but not neutral ground truth.

## Related pages

- [[deepest]]
- [[seen-and-unseen-emotion-transfer]]
- [[ser-perceptual-loss]]
- [[emotion-embedding-loss]]
- [[evaluation-metrics-for-voice-conversion]]
