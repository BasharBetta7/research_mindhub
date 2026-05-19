# LaTeX Paper Workspace

This folder holds the IEEE Access manuscript draft.

## Build

From `paper/latex`:

```bash
make
```

The PDF is written to `build/main.pdf`.

To rebuild automatically whenever `main.tex` or a section file is saved:

```bash
make watch
```

Keep that terminal open while writing. Press `Ctrl+C` to stop watching.

## IEEE Access Template

Place the official IEEE Access LaTeX template files in `access/`, especially `ieeeaccess.cls`.
The local `latexmkrc` adds `access/` to the TeX search path.

## Main Files

- `main.tex` - manuscript entry point.
- `sections/` - one source file per paper section.
- `figures/` - generated figures and author photos.
- `tables/` - table fragments if needed.
- `../../sources.bib` - shared project bibliography.

## Writing Rule

Keep the paper framed as a measurement paper unless new experiments provide matched external baselines.
The current safest thesis is that speaker--emotion tradeoffs are measurable and condition-dependent.
