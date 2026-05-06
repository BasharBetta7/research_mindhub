# Style Pretraining For EVC

**Summary**: Style pretraining initializes emotional voice conversion models using a larger neutral multi-speaker TTS corpus. Emovox uses it to reduce reliance on limited emotional speech data.

**Sources**:
- Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf

**Last updated**: 2026-05-06

---

## Motivation

Sequence-to-sequence emotional voice conversion usually needs substantial emotional speech data to learn robust attention alignment and emotional intelligibility (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). Emovox uses style pretraining to reduce the amount of emotional speech needed for training (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Method

During style pretraining, Emovox trains a multi-speaker sequence-to-sequence TTS-style framework on neutral speech to disentangle speaker style from linguistic content (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). The style encoder learned on the TTS corpus is then used as the pretrained emotion encoder for emotion training (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Evidence

The paper reports that Emovox without style pretraining has the worst MCD and DDUR among the compared systems in Table 1 (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf). This supports the claim that style pretraining is important for Emovox under limited emotional training data (source: Zhou et al. - 2023 - Emotion Intensity and its Control for Emotional Voice Conversion.pdf).

## Related pages

- [[emovox]]
- [[sequence-to-sequence-emotional-voice-conversion]]
- [[emotion-intensity-control]]
