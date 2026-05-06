# EVC-CLAP

**Summary**: EVC-CLAP is the contrastive language-audio pretraining component in ClapFM-EVC. It aligns emotional speech and natural-language emotion prompts so EVC can be controlled by text or reference audio.

**Sources**:
- Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf

**Last updated**: 2026-05-06

---

## Definition

EVC-CLAP is an emotional contrastive language-audio pretraining model used inside [[clapfm-evc]] (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). It uses a HuBERT-based audio encoder and an XLM-RoBERTa-based text encoder to embed speech and natural-language emotion prompts into a shared emotion space (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Training

EVC-CLAP is trained with soft labels derived from categorical emotion labels and natural-language prompt labels (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). The paper uses a symmetric KL contrastive loss to align audio and text emotional representations (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf).

## Role In EVC

During inference, EVC-CLAP can generate target emotional embeddings from a prompt or reference speech for use by AdaFM-VC (source: Pan et al. - 2025 - ClapFM-EVC High-Fidelity and Flexible Emotional Voice Conversion with Dual Control from Natural Lan.pdf). This makes it the bridge between [[natural-language-emotion-control]] and emotional voice conversion.

## Related pages

- [[clapfm-evc]]
- [[natural-language-emotion-control]]
- [[freestyle-emotion-prompting]]
- [[emotion-intensity-control]]

