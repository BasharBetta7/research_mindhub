# Seq2Seq CycleGAN EVC

**Summary**: Didi et al. proposes a hybrid EVC system that uses Seq2Seq temporal modelling followed by CycleGAN spectral refinement. The source is relevant to method design and tradeoff metrics, but its ESD description conflicts with the canonical ESD paper and should be cited cautiously.

**Sources**:
- Didi+et+al.pdf
- Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf

**Last updated**: 2026-05-06

---

## Caution

The Didi et al. source describes ESD as containing recordings from over 300 speakers, but the canonical ESD paper reports 10 native English speakers and 10 native Chinese speakers (source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf). This contradiction means Didi et al. should be used cautiously for architectural ideas and reported metrics, not as authority on ESD metadata (source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Method

The proposed framework operates in the Mel-spectrogram domain and combines Seq2Seq temporal modelling with CycleGAN-based spectral refinement (source: Didi+et+al.pdf). The Seq2Seq encoder-decoder with attention generates a coarse emotion-aware Mel representation, and the CycleGAN module refines that representation through adversarial, cycle-consistency, and identity-preservation losses (source: Didi+et+al.pdf).

The method extracts Mel-spectrogram and F0 features, uses a Tacotron-style encoder-decoder with LSTM layers and location-sensitive attention, and then applies residual-convolutional CycleGAN generators with PatchGAN discriminators (source: Didi+et+al.pdf). A neural vocoder reconstructs waveform from the refined Mel-spectrogram (source: Didi+et+al.pdf).

## Evaluation

The paper reports objective metrics including MCD, F0 RMSE, SSIM, and speaker similarity based on x-vector cosine similarity (source: Didi+et+al.pdf). It also reports subjective MOS for naturalness and emotional similarity, comparing Seq2Seq-only, CycleGAN-only, and the proposed hybrid system (source: Didi+et+al.pdf).

In the reported table, the proposed hybrid system improves MCD from 4.05 for Seq2Seq-only and 4.20 for CycleGAN-only to 3.85, improves F0 RMSE from 0.34 and 0.36 to 0.28, improves SSIM from 0.79 and 0.76 to 0.84, and improves speaker similarity from 0.83 and 0.81 to 0.88 (source: Didi+et+al.pdf). These metrics make the source relevant to [[speaker-identity-evaluation-in-evc]], but the dataset contradiction should remain visible when citing it (source: Didi+et+al.pdf; source: Zhou et al. - 2022 - Emotional voice conversion Theory, databases and ESD.pdf).

## Tradeoff relevance

Didi et al. is relevant to [[speaker-emotion-tradeoff]] because it reports speaker similarity alongside emotional expressiveness and F0 metrics (source: Didi+et+al.pdf). It does not establish a controlled tradeoff curve, because it compares architectures rather than sweeping emotion strength or speaker-preservation constraints (source: Didi+et+al.pdf).

## Related pages

- [[sequence-to-sequence-emotional-voice-conversion]]
- [[cyclegan-evc]]
- [[seq2seq-cyclegan-refinement]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[evaluation-metrics-for-voice-conversion]]
- [[f0-pitch-contour-in-voice-conversion]]
- [[esd-dataset]]
