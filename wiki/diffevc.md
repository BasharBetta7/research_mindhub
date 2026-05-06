# DiffEVC

**Summary**: DiffEVC is an any-to-any emotional voice conversion system that uses a diffusion decoder, disentangled speaker and emotion encoders, and expressive guidance. It is directly relevant to the speaker-emotion tradeoff because it evaluates emotion conversion, speaker similarity, quality, and guidance-based emotion strength together.

**Sources**:
- Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf

**Last updated**: 2026-05-06

---

## Metadata note

The raw filename refers to ZSDEVC and 2025, but the PDF title is "DiffEVC: Any-to-Any Emotion Voice Conversion with Expressive Guidance" and the arXiv identifier shown in the PDF is 2409.03636v1 from 2024 (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). The wiki page uses the title printed in the PDF because that is the paper identity visible in the source file (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Task

DiffEVC targets any-to-any emotional voice conversion, where source and reference speech can differ in speaker, lexical content, and emotion, and the speakers may be unseen during training (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). The model aims to preserve source linguistic content and source speaker identity while transferring emotion from a reference utterance (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Architecture

The system uses a phoneme or content encoder, a speaker encoder, an emotion encoder, and a diffusion decoder conditioned on content, speaker, and emotion representations (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). The speaker encoder is based on a pretrained speaker-verification d-vector representation, while the emotion encoder uses a Wav2Vec2-Large-Robust speech emotion recognition model fine-tuned on MSP-Podcast (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

DiffEVC adds [[mutual-information-disentanglement]] between speaker and emotion representations using a vCLUB-style mutual-information estimator (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). This makes the paper important for [[speaker-disentanglement]], because the model explicitly tries to reduce speaker information inside the emotion representation and emotion information inside the speaker representation (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Expressive guidance

The paper introduces [[expressive-guidance]], an inference-time guidance mechanism that pushes the reverse diffusion process toward the desired source-speaker/reference-emotion condition and away from a negative condition (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). The guidance scale can be set above 1, making DiffEVC relevant to [[emotion-intensity-control]] because the method manipulates not only the target emotion label but also the strength of the guidance signal (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Data and evaluation

DiffEVC trains on MSP-Podcast v1.10 and evaluates on MSP-Podcast v1.11 and ESD, with angry, happy, sad, and neutral categories used in the reported emotional conversion experiments (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). The evaluation includes UTMOS, DNSMOS, SECS, ECA, ERA, and subjective MOS-style ratings, which makes the paper useful for [[evaluation-metrics-for-voice-conversion]] (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

The reported ablations compare a diffusion-only system, the total disentanglement loss, negative speaker conditioning, negative emotion conditioning, and expressive guidance (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). On MSP-Podcast, the paper reports that emotion conversion accuracy improves from 0.701 in the base diffusion model to 0.812 with the total disentanglement loss and 0.852 with expressive guidance, while SECS changes from 0.821 in the base model to 0.757 with the total loss and 0.746 with expressive guidance (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). This is direct evidence that stronger emotion mechanisms should be read alongside speaker-similarity metrics rather than in isolation (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Tradeoff relevance

DiffEVC is one of the most directly relevant sources for [[speaker-emotion-tradeoff]] because it explicitly separates speaker and emotion representations, adds a disentanglement loss, and reports both emotion and speaker-side metrics (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf). It still does not fully close the tradeoff gap, because the paper reports ablations and guidance variants rather than a systematic Pareto sweep of guidance strength against speaker similarity (source: Chou et al. - 2025 - ZSDEVC Zero-Shot Diffusion-based Emotional Voice Conversion with Disentangled Mechanism.pdf).

## Related pages

- [[diffusion-based-emotion-conversion]]
- [[expressive-guidance]]
- [[mutual-information-disentanglement]]
- [[speaker-emotion-tradeoff]]
- [[speaker-identity-evaluation-in-evc]]
- [[emotion-intensity-control]]
- [[in-the-wild-emotion-conversion]]
- [[evaluation-metrics-for-voice-conversion]]
