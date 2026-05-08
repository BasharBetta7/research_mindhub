# Model Inferred Intensity Gap Analysis

**Summary**: The expanded `MODEL_inferred_intensity` experiments strengthen the evidence for an alpha-driven emotion-speaker tradeoff on ESD, especially when listening-study scores are included. The largest remaining gaps are cross-dataset consistency, target-speaker evaluation, acoustic intensity validation, and reproducible baselines.

**Sources**:
- `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/alpha_metrics_summary.csv`
- `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/alpha_metrics_by_emotion_summary.csv`
- `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/intensity_per_sample_metrics.csv`
- `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/alpha_metrics_comparison.png`
- `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/summary.md`
- `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/baseline_frontier_dominance.csv`
- `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_summary.csv`
- `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_by_emotion_summary.csv`
- `exp/MODEL_inferred_intensity/ESD/DSST/intensity_per_sample_metrics.csv`
- `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_comparison.png`
- `exp/MODEL_inferred_intensity/ESD/DSST/summary.md`
- `exp/MODEL_inferred_intensity/ESD/DSST/baseline_frontier_dominance.csv`
- `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_overall_summary.csv`
- `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_alpha_summary.csv`
- `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_emotion_summary.csv`
- `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_speaker_summary.csv`
- `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_metrics_vs_alpha.png`
- `exp/MODEL_inferred_intensity/CREMA_D/pretrained/alpha_metrics_summary.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/pretrained/alpha_metrics_by_emotion_summary.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/pretrained/intensity_per_sample_metrics.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/pretrained/summary.md`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/alpha_metrics_summary.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/alpha_metrics_by_emotion_summary.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/intensity_per_sample_metrics.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/alpha_metrics_comparison.png`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/summary.md`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/baseline_frontier_dominance.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/alpha_metrics_summary.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/alpha_metrics_by_emotion_summary.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/intensity_per_sample_metrics.csv`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/alpha_metrics_comparison.png`
- `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/summary.md`

**Last updated**: 2026-05-07

---

## Scope

This page extends [[model-inferred-intensity-alpha-critique]] by comparing five operating conditions: ESD same-speaker same-text, ESD different-speaker same-text, CREMA-D pretrained, CREMA-D finetuned at epoch 30, and CREMA-D finetuned at epoch 75 (source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/intensity_per_sample_metrics.csv`; source: `exp/MODEL_inferred_intensity/ESD/DSST/intensity_per_sample_metrics.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/pretrained/intensity_per_sample_metrics.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/intensity_per_sample_metrics.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/intensity_per_sample_metrics.csv`).

The ESD same-speaker condition has 4,800 rows over 10 speakers and four target emotions, while ESD different-speaker has 6,480 rows over 10 speakers and four target emotions (source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/intensity_per_sample_metrics.csv`; source: `exp/MODEL_inferred_intensity/ESD/DSST/intensity_per_sample_metrics.csv`). The CREMA-D conditions each have 4,752 rows over 24 speakers and three target emotions: Angry, Happy, and Sad (source: `exp/MODEL_inferred_intensity/CREMA_D/pretrained/intensity_per_sample_metrics.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/intensity_per_sample_metrics.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/intensity_per_sample_metrics.csv`).

## Cross-Condition Result

The ESD same-speaker same-text setting shows the cleanest alpha frontier: emotion accuracy rises from 0.199 to 0.664, emotion-reference cosine rises from -0.038 to 0.622, and source-speaker cosine falls from 0.780 to 0.680 between alpha 0.0 and 1.0 (source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/alpha_metrics_summary.csv`). The ESD different-speaker same-text setting shows the same direction but a steeper speaker cost: emotion accuracy rises from 0.198 to 0.537, while source-speaker cosine falls from 0.782 to 0.591 (source: `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_summary.csv`).

This is important for [[speaker-emotion-tradeoff]] because the different-speaker condition moves closer to the real EVC question than the original same-speaker critique. It suggests that the alpha-driven emotion gain remains measurable when source and reference speakers differ, but the speaker-side cost becomes larger (source: `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_summary.csv`).

![ESD different-speaker alpha metrics](../exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_comparison.png)

## Listening-Study Evidence

The ESD listening-study results support the objective alpha trend. As alpha increases from 0.0 to 1.0, mean emotion-similarity score rises from 2.07 to 3.46, while mean speaker-similarity score drops from 4.04 to 1.55 and mean naturalness drops from 2.79 to 2.41 (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_alpha_summary.csv`). Across the four listening-study alpha points, alpha correlates strongly with emotion similarity and negatively with speaker similarity and naturalness (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_alpha_summary.csv`).

![Listening scores by alpha](../exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_metrics_vs_alpha.png)

The listening scores also agree with the automatic ESD SSST metrics at the alpha points that were rated. Emotion-similarity score tracks objective emotion accuracy and emotion-reference cosine, while speaker-similarity score tracks objective source-speaker cosine (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_alpha_summary.csv`; source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/alpha_metrics_summary.csv`). This is a major improvement over relying only on automatic emotion classifiers.

The listening-study gap is sample coverage and design. Only alpha 0.0, 0.4, 0.8, and 1.0 appear in the user-vote summary, with about 96-100 votes per alpha, while alpha 0.2 and 0.6 are absent from the human ratings (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_alpha_summary.csv`). The study also aggregates mean scores but does not document listener identity, trial balancing, confidence intervals, or statistical tests in the available summary files (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_overall_summary.csv`).

## Emotion-Specific Gaps

The tradeoff is not uniform across emotions. In ESD same-speaker, Sad starts high and ends high, from 0.660 to 0.970 emotion accuracy, while Angry rises from 0.050 to 0.520 and Surprise rises from 0.000 to 0.510 (source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/alpha_metrics_by_emotion_summary.csv`). In ESD different-speaker, Angry remains weak even at alpha 1.0, rising only from 0.000 to 0.152, while Happy reaches 0.644 and Sad reaches 0.993 (source: `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_by_emotion_summary.csv`).

The speaker penalty is also emotion-dependent. In ESD different-speaker, source-speaker cosine drops by about -0.168 for Angry, -0.164 for Happy, -0.213 for Sad, and -0.220 for Surprise from alpha 0.0 to 1.0 (source: `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_by_emotion_summary.csv`). This means a single alpha cannot be assumed to define the same emotion-speaker compromise for all emotions.

The human ratings reinforce this imbalance. Sad has the highest mean emotion-similarity score at 3.56 and the highest speaker-similarity score at 3.40, while Surprise has the lowest emotion-similarity score at 2.55 and lowest speaker-similarity score at 2.05 (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_emotion_summary.csv`). This suggests Surprise remains the hardest ESD target and should be analyzed separately rather than hidden inside aggregate metrics.

## CREMA-D Generalization

CREMA-D does not reproduce the ESD tradeoff shape cleanly. In the pretrained CREMA-D run, emotion accuracy rises from 0.313 to 0.561 and emotion-reference cosine rises from 0.340 to 0.550, but speaker cosine only falls from 0.636 to 0.625 (source: `exp/MODEL_inferred_intensity/CREMA_D/pretrained/alpha_metrics_summary.csv`). In the finetuned epoch-30 run, emotion accuracy rises from 0.327 to 0.518 and emotion-reference cosine rises from 0.354 to 0.543, while speaker cosine falls only from 0.621 to 0.606 (source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/alpha_metrics_summary.csv`).

![CREMA-D finetuned epoch-30 alpha metrics](../exp/MODEL_inferred_intensity/CREMA_D/finetuned/alpha_metrics_comparison.png)

The CREMA-D epoch-75 run looks like a bad or mismatched checkpoint for this analysis. Emotion accuracy slightly decreases from 0.326 to 0.312 between alpha 0.0 and 1.0, emotion-reference cosine stays low from 0.162 to 0.194, emotion-source cosine is already negative, and speaker cosine is low, dropping from 0.386 to 0.346 (source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/alpha_metrics_summary.csv`).

![CREMA-D finetuned epoch-75 alpha metrics](../exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/alpha_metrics_comparison.png)

This is not evidence against the ESD tradeoff. It is a generalization warning: the alpha mechanism behaves differently across datasets/checkpoints, and CREMA-D needs a dataset-specific explanation before being used as confirmation of the same frontier.

## Baseline Gap

All `baseline_frontier_dominance.csv` files are empty, and the summary files say no external baselines were provided (source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/summary.md`; source: `exp/MODEL_inferred_intensity/ESD/DSST/summary.md`; source: `exp/MODEL_inferred_intensity/CREMA_D/pretrained/summary.md`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/summary.md`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/summary.md`). Therefore, the current analysis can compare operating points within this method, but it cannot yet claim that the method dominates or matches external EVC baselines.

This is a major gap if the goal is a paper-level argument. The current evidence can support "alpha traces an internal operating curve," but not "this method is Pareto-superior to existing methods."

## Metric And Reproducibility Gaps

The same `speaker_ref_cosine` issue remains visible across newer runs. In same-speaker settings, `speaker_ref_cosine` is 1.0 at alpha 0.0 for CREMA-D and then declines with alpha, even though the reference waveform should not change across generated alpha settings (source: `exp/MODEL_inferred_intensity/CREMA_D/pretrained/alpha_metrics_summary.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/alpha_metrics_summary.csv`). In ESD DSST, `speaker_ref_cosine` drops from 1.0 to 0.450 as alpha increases, which suggests it is not simply a fixed source-reference property (source: `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_summary.csv`).

This does not invalidate `speaker_cosine`, but it means `speaker_ref_cosine` should not be used as a core tradeoff metric until the computation is clarified. The safer speaker-side metric in the current evidence is source-output `speaker_cosine`, supported by the listening-study speaker-similarity trend (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_alpha_summary.csv`; source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/alpha_metrics_summary.csv`).

The experiment still lacks acoustic intensity diagnostics. [[emotion-intensity-control]] notes that emotion intensity can appear through pitch, energy, duration, speech rate, and prosodic dynamics, not only through emotion classifier confidence. The current experiment measures emotion accuracy, confidence, emotion-reference cosine, emotion-source cosine, and speaker cosine, but not F0 range, energy, duration, speaking rate, or voiced-ratio changes (source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/intensity_per_sample_metrics.csv`).

## Research Gaps

1. Cross-speaker target identity is still not fully isolated. ESD DSST is closer to EVC than SSST, but the available metrics mainly report source-output speaker cosine rather than target-speaker similarity, source-speaker leakage, and reference-speaker leakage as separate axes (source: `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_summary.csv`).

2. Surprise and Angry need targeted error analysis. Surprise is weak in ESD listening results, and Angry is especially weak in ESD DSST at alpha 1.0 (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_emotion_summary.csv`; source: `exp/MODEL_inferred_intensity/ESD/DSST/alpha_metrics_by_emotion_summary.csv`).

3. CREMA-D needs an explanation before it is used as generalization evidence. The pretrained and epoch-30 finetuned runs show emotion gains with small speaker loss, while epoch 75 mostly fails to improve emotion under alpha (source: `exp/MODEL_inferred_intensity/CREMA_D/pretrained/alpha_metrics_summary.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/alpha_metrics_summary.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/epoch75/alpha_metrics_summary.csv`).

4. Human evaluation needs statistical framing. The listening study supports the frontier direction, but the current summaries do not show confidence intervals, listener-level mixed effects, significance tests, or whether samples were balanced by speaker/emotion/alpha (source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_by_alpha_summary.csv`; source: `exp/MODEL_inferred_intensity/ESD/listening_study_results/user_votes_overall_summary.csv`).

5. External baselines are missing. The empty baseline-dominance files mean the frontier is internal to the proposed alpha control and cannot yet be compared to published systems or ablations (source: `exp/MODEL_inferred_intensity/ESD/SSST/full_set_alpha_variants/baseline_frontier_dominance.csv`; source: `exp/MODEL_inferred_intensity/ESD/DSST/baseline_frontier_dominance.csv`; source: `exp/MODEL_inferred_intensity/CREMA_D/finetuned/baseline_frontier_dominance.csv`).

## Recommended Next Analysis

1. For ESD DSST, compute three speaker metrics per sample: source-output cosine, reference-output cosine, and source-reference cosine. This would separate source preservation, target/reference leakage, and baseline pair similarity.

2. Add F0, energy, duration, and speaking-rate summaries by alpha and emotion, then test whether alpha is truly an intensity control or mostly a classifier-targetness control.

3. Run confusion matrices by alpha for ESD DSST and CREMA-D, then inspect Angry and Surprise failures manually.

4. Reanalyze listening votes with confidence intervals and, if listener IDs exist, a mixed-effects model with alpha, target emotion, and speaker as factors.

5. Add external or internal baselines to the `baseline_frontier_dominance.csv` workflow, such as neutral reconstruction, direct reference-copy upper/lower bounds, no-style-control ablation, and the best fixed checkpoint without alpha control.

## Related pages

- [[model-inferred-intensity-alpha-critique]]
- [[speaker-emotion-tradeoff]]
- [[emotion-intensity-control]]
- [[objective-speech-evaluation-metrics]]
- [[speaker-similarity-metrics]]
- [[evaluation-metrics-for-voice-conversion]]
