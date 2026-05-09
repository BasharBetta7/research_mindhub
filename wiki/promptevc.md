# PromptEVC

**Summary**: PromptEVC is a controllable emotional voice conversion system that uses natural-language prompts to specify target emotion, intensity, mixed emotion, pitch, speed, and volume. It is directly relevant to [[emotion-intensity-control]], but its control interface is semantic prompts rather than a single scalar intensity value.

**Sources**:
- Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf

**Last updated**: 2026-05-08

---

## Task

PromptEVC addresses controllable emotional voice conversion, where the system changes the emotional expression of a source utterance while preserving linguistic content and speaker identity (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). The paper argues that previous controllable EVC interfaces based on labels, reference speech, or numeric values can be less intuitive because people describe emotional speech with subjective natural-language descriptions (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

The method is a direct EVC source rather than an emotional TTS source, because it takes source speech and controls the converted emotional expression with text prompts (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). This places PromptEVC near [[clapfm-evc]] and [[zest]], but its distinctive interface is user-written emotion descriptions rather than only reference speech or prompt-retrieved references (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Architecture

PromptEVC is built on a conditional variational autoencoder framework with adversarial waveform reconstruction (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). Its main modules are a text-emotion mapping module, a prosody modeling and control module, a speaker encoder for identity preservation, and a decoder for waveform reconstruction (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

The text-emotion mapping module uses RoBERTa as an emotion descriptor to produce an initial text emotion embedding, then uses a diffusion-based prompt mapper to align this embedding with an Emotion2Vec reference embedding (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). During inference, the prompt-mapped embedding is used as the emotional representation, making [[emotion2vec]] part of the training bridge between text prompts and speech emotion representations (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

The prosody module extracts HuBERT units, deduplicates repeated tokens, predicts duration, and combines content and emotion to model pitch, duration, and energy-related prosody (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). This makes PromptEVC relevant to [[duration-flexible-evc]] and [[spectrum-prosody-conversion]], because rhythm and prosody are treated as central carriers of emotional expression (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Dataset and Prompt Preparation

PromptEVC evaluates on TextrolSpeech, which the paper describes as 330 hours of audio with 236,203 natural text-description and speech pairs (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). The emotional subset contains 42,909 emotional samples across angry, contempt, disgusted, fear, happy, sad, and surprised categories, with remaining non-emotional samples labeled neutral (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

The paper derives emotional intensity labels with relative attribute ranking and groups samples into high, medium, and low intensity levels using the top 30 percent, middle 40 percent, and bottom 30 percent of ranked values (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). It then rewrites TextrolSpeech style prompts with ChatGPT-4 using emotion category, emotional intensity, pitch, speaking speed, and volume while removing gender-specific information to support speaker preservation (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Evaluation

The paper compares PromptEVC against Textless-EVC, ZEST, Emovox, and Mixed-EVC (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). In the main table, PromptEVC reports MCD 4.70, CER 4.09, RMSE-F0 42.58, SER classification accuracy 99.32, naturalness MOS 4.22, and emotional similarity 81.30 percent (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

For controllability, the paper evaluates emotional intensity, mixed emotion, pitch, speaking speed, and volume using both a pretrained classifier and five human annotators (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). Reported objective classification accuracy is 77.58 percent for emotional intensity, 61.25 percent for mixed emotion, 86.41 percent for pitch, 89.72 percent for speed, and 91.52 percent for volume (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Relevance to the Tradeoff

PromptEVC is important for the [[speaker-emotion-tradeoff]] because it increases the number of controllable emotional dimensions beyond a single target emotion or intensity value (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). However, its speaker preservation evidence is incomplete for the tradeoff question because the main evaluation does not report standard speaker-similarity metrics such as SECS, EER, or sMOS (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

The speaker encoder ablation shows that removing the speaker encoder raises RMSE-F0, but RMSE-F0 is only an indirect proxy for speaker identity and should not be treated as a full speaker-similarity measurement (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf). For this wiki, PromptEVC should therefore be treated as strong evidence for [[natural-language-emotion-control]] and partial evidence for speaker-preserving controllable EVC (source: Qi et al. - 2025 - PromptEVC Controllable Emotional Voice Conversion with Natural Language Prompts.pdf).

## Related pages

- [[natural-language-emotion-control]]
- [[emotion-intensity-control]]
- [[freestyle-emotion-prompting]]
- [[emotion2vec]]
- [[speaker-identity-evaluation-in-evc]]
- [[speaker-emotion-tradeoff]]
- [[clapfm-evc]]
- [[einet]]
- [[emovox]]
- [[zest]]
- [[textless-speech-emotion-conversion]]
- [[mixed-emotion-synthesis]]
