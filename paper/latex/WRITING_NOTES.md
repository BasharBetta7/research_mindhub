# Writing Notes

## Safe Thesis

Increasing target-emotion strength through alpha-controlled emotional voice conversion reveals a measurable speaker--emotion frontier, but the frontier is condition-dependent.

## Claims Currently Supported

- ESD SSST and DSST show emotion gains with speaker-similarity loss.
- ESD SSST has listening-study support in the same direction as the automatic metrics.
- CREMA-D pretrained and finetuned show much flatter speaker-loss behavior than ESD.
- CycleGAN is a useful high-emotion, higher-drift baseline, not the preferred speaker-preserving method.
- The no-style-loss increased-rank-lambda ablation shows that highly emotion-separable style embeddings do not guarantee a better conversion frontier.

## Claims to Avoid

- Do not claim the method beats published EVC systems without matched baselines.
- Do not claim stronger emotion always causes speaker drift.
- Do not claim automatic emotion embeddings fully measure perceived emotional quality.
- Do not hide weak angry and surprise behavior behind aggregate metrics.

## Missing Before Submission

- Replace author placeholders and affiliation.
- Add actual citations in `sources.bib` to every related-work claim.
- Generate final frontier plots and table fragments.
- Verify MCD scaling before reporting MCD.
- Add listening-study details: number of raters, protocol, scale, and statistics.
- Fix or explain the CycleGAN DSST validation expected-row mismatch before final paper tables.
