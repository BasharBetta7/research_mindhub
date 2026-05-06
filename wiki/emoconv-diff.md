# EmoConv-Diff

**Summary**: EmoConv-Diff is a diffusion-based speech emotion conversion model for non-parallel, in-the-wild speech. It converts continuous arousal while preserving lexical content and speaker identity.

**Sources**:
- Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf

**Last updated**: 2026-05-06

---

## Problem framing

EmoConv-Diff defines speech emotion conversion as changing the expressed emotion of an utterance while preserving lexical content and speaker identity (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). Unlike many prior systems, it targets non-parallel and in-the-wild speech rather than acted parallel corpora (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

The paper represents emotion with continuous arousal on a 1 to 7 scale, which gives direct intensity control without categorical emotion labels (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This makes the paper central to [[arousal-based-emotion-control]] and [[in-the-wild-emotion-conversion]].

## Model

The model uses separate encoders for phoneme content, speaker identity, and emotion, then uses a diffusion-based decoder to synthesize a mel spectrogram conditioned on those attributes (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). The phoneme encoder produces speaker- and emotion-independent average-voice features, the speaker encoder uses a pretrained speaker verification model, and the emotion encoder uses a pretrained SSL-based SER model (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

During training, the diffusion model reconstructs the source utterance while conditioning on its emotion (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). During inference, a target emotion embedding is used to convert the source utterance toward the target arousal (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

## Data

The paper trains and validates on MSP-Podcast v1.10, described as about 238 hours of in-the-wild audio with more than 1400 speakers and utterance-level arousal annotations (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). The authors contrast this with ESD, which they describe as about 29 hours of acted speech from 10 English speakers (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

## Results

The best EmoConv-Diff variant reports SER Lmse 0.072 and Labs 21%, improving over the HiFiGAN baseline values of 0.084 and 24% (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). The same variant reports DNSMOS SIG 3.21 and OVRL 2.78, which is on par with the HiFiGAN baseline's SIG 3.21 and OVRL 2.79 (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

The paper reports that EmoConv-Diff improves most at extreme target arousal values 1 and 7, which the authors identify as a common challenge for speech emotion conversion systems (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

## Caution

The paper mostly demonstrates control over arousal rather than full categorical emotion or valence (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). Since the authors state that audio captures arousal better than valence, EmoConv-Diff should not be overread as complete fine-grained emotion conversion (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

The evaluation uses SER prediction error and DNSMOS because parallel references are unavailable in the in-the-wild setting (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf). This is reasonable for the setup, but it leaves open how human listeners perceive speaker preservation, naturalness, and target emotion quality.

For [[speaker-identity-evaluation-in-evc]], EmoConv-Diff should be treated as partial evidence: it encodes speaker identity with a pretrained speaker verification model, but the reported results do not provide a detailed speaker-similarity or speaker-drift analysis (source: Prabhu et al. - 2024 - EMOCONV-DIFF Diffusion-based Speech Emotion Conversion for Non-parallel and In-the-wild Data.pdf).

## Related pages

- [[diffusion-based-emotion-conversion]]
- [[in-the-wild-emotion-conversion]]
- [[arousal-based-emotion-control]]
- [[emotional-speech-conversion]]
- [[emotion-intensity-control]]
- [[evaluation-metrics-for-voice-conversion]]
- [[speaker-emotion-tradeoff]]
- [[ser-perceptual-loss]]
- [[speaker-identity-evaluation-in-evc]]
