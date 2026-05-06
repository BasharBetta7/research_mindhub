# Information Bottleneck For Voice Conversion

**Summary**: The information bottleneck in AutoVC constrains the content representation so it retains linguistic/prosodic content while discarding speaker identity. Its width controls the tradeoff between reconstruction and speaker disentanglement.

**Sources**:
- Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf

**Last updated**: 2026-05-06

---

## Definition

In [[autovc]], the information bottleneck is the restricted content code produced by the content encoder (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). The bottleneck is implemented through dimensionality reduction and temporal downsampling of bidirectional LSTM outputs (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Tradeoff

If the bottleneck is too wide, the content embedding can carry source speaker information and harm conversion (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). If the bottleneck is too narrow, content information is lost and reconstruction becomes poor (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). The desired setting is narrow enough for [[speaker-disentanglement]] while still wide enough for good reconstruction (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Evidence

The AutoVC bottleneck analysis reports that a narrow model has reconstruction error 34.6 and speaker classification accuracy 7.50%, the normal AutoVC model has reconstruction error 8.59 and accuracy 12.0%, and the wide model has reconstruction error 3.85 and accuracy 70.5% (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf). This supports the claim that widening the bottleneck improves reconstruction but leaks speaker identity (source: Qian et al. - 2019 - AUTOVC Zero-Shot Voice Style Transfer with Only Autoencoder Loss.pdf).

## Related pages

- [[autovc]]
- [[autoencoder-voice-conversion]]
- [[speaker-disentanglement]]
- [[zero-shot-voice-conversion]]
