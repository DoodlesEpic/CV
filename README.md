# CV

This repository contains the LaTeX source code for my curriculum vitae, available in two languages:

- `cv.tex` — Portuguese (Brazil)
- `cv-en.tex` — English

Both documents are single-page résumés typeset with the Charter font, sharing the same layout and built entirely with packages available in any standard LaTeX distribution.

## Building

To build this project, you will need a LaTeX distribution installed on your system:

- **Linux**: [TeX Live](https://www.tug.org/texlive/), available on most package managers
- **Windows**: [MiKTeX](https://miktex.org/) or TeX Live
- **macOS**: [MacTeX](https://www.tug.org/mactex/)

On Debian-based distributions, the required packages are covered by:

```
sudo apt install texlive-latex-extra texlive-fonts-recommended texlive-lang-portuguese
```

To compile the documents to PDF, run:

```
pdflatex cv.tex
pdflatex cv-en.tex
```

The output will be written to `cv.pdf` and `cv-en.pdf`. A single pass is enough, as the documents have no bibliography or cross-references.

Alternatively, if you have `latexmk` installed, you can let it handle the compilation:

```
latexmk -pdf cv.tex cv-en.tex
```

## Continuous Integration

Every push to the `main` branch triggers a GitHub Actions workflow that compiles both documents using [latex-action](https://github.com/xu-cheng/latex-action). The resulting PDFs are uploaded as build artifacts — `curriculo-eduardo-moraes` (Portuguese) and `resume-eduardo-moraes-en` (English) — which you can download from the workflow run page under the Actions tab. Note that artifacts expire after 90 days, so for a permanent copy use the release below.

The same run then publishes a GitHub release tagged `v<run number>` with both `cv.pdf` and `cv-en.pdf` attached, so the latest release always holds the current version of each CV. The workflow can also be started manually from the Actions tab.

The workflow is defined in `.github/workflows/build.yml`.

## Dependencies

The documents use only standard packages: `geometry`, `enumitem`, `titlesec`, `xcolor`, `hyperref`, `babel` (brazil and english), and `charter`. No external fonts or custom classes are required.

## License

This project is proprietary. All rights reserved.
