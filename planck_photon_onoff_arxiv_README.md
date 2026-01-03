## arXiv LaTeX source (Planck time / photon on-off paper)

### Files
- **Main LaTeX**: `docs/planck_photon_onoff_arxiv.tex`

### Local build (PDF)

If you have a TeX distribution installed (MiKTeX on Windows, TeX Live on Linux, MacTeX on macOS), run from the repo root:

```bash
pdflatex -interaction=nonstopmode -halt-on-error -file-line-error -output-directory docs docs/planck_photon_onoff_arxiv.tex
pdflatex -interaction=nonstopmode -halt-on-error -file-line-error -output-directory docs docs/planck_photon_onoff_arxiv.tex
```

This produces `docs/planck_photon_onoff_arxiv.pdf`.

### arXiv submission

Upload at minimum:
- `planck_photon_onoff_arxiv.tex` (you can rename `docs/planck_photon_onoff_arxiv.tex` to that for submission)

This draft uses `thebibliography` (no external `.bib` required), which is arXiv-friendly.


