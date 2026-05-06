# Prosody Embedding Decomposition

**Summary**: Prosody embedding decomposition manipulates a learned prosody latent space to simulate emotional structure. Daisy-TTS uses this idea to synthesize primary emotions, mixed emotions, intensity levels, and emotion polarity.

**Sources**:
- Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf

**Last updated**: 2026-05-06

---

## Definition

Prosody embedding decomposition represents a learned prosody embedding as a mean plus weighted prototype directions, then manipulates the weights to synthesize desired emotional prosody (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). In Daisy-TTS, the prototypes are obtained by applying PCA to emotionally separable prosody embeddings (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

## Emotional Operations

Primary emotions are simulated by sampling weights around the embedding region of a target primary emotion (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). Secondary emotions are simulated by mixing the distributions of two primary emotions (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

Intensity is controlled by scaling the weighted basis directions, where lower scaling weakens expression and higher scaling intensifies expression (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). Polarity is simulated by negating primary-emotion weights, such as using the negative of joy to produce a sadness-like emotion (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf).

## Relevance

This concept is relevant to [[mixed-emotion-synthesis]], [[emotion-intensity-control]], and [[spectrum-prosody-conversion]] because it treats emotion control as manipulation of prosodic structure rather than only class labels (source: Chevi and Aji - 2024 - Daisy-TTS Simulating Wider Spectrum of Emotions via Prosody Embedding Decomposition.pdf). It remains TTS evidence unless adapted and evaluated in an EVC setting.

## Related pages

- [[daisy-tts]]
- [[mixed-emotion-synthesis]]
- [[emotion-intensity-control]]
- [[spectrum-prosody-conversion]]

