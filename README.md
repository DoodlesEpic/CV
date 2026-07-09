# CV

This repository contains the LaTeX source code for my curriculum vitae. The document is a single-page résumé typeset with the Charter font, built entirely with packages available in any standard LaTeX distribution.

## Building

To build this project, you will need a LaTeX distribution installed on your system:

- **Linux**: [TeX Live](https://www.tug.org/texlive/), available on most package managers
- **Windows**: [MiKTeX](https://miktex.org/) or TeX Live
- **macOS**: [MacTeX](https://www.tug.org/mactex/)

On Debian-based distributions, the required packages are covered by:

```
sudo apt install texlive-latex-extra texlive-fonts-recommended texlive-lang-portuguese
```

To compile the document to PDF, run:

```
pdflatex cv.tex
```

The output will be written to `cv.pdf`. A single pass is enough, as the document has no bibliography or cross-references.

Alternatively, if you have `latexmk` installed, you can let it handle the compilation:

```
latexmk -pdf cv.tex
```

## Continuous Integration

Every push to the `main` branch triggers a GitHub Actions workflow that compiles the document using [latex-action](https://github.com/xu-cheng/latex-action). The resulting PDF is uploaded as a build artifact, which you can download from the workflow run page under the Actions tab. Note that artifacts expire after 90 days, so for a permanent copy compile the document locally.

The workflow is defined in `.github/workflows/build.yml`.

## Dependencies

The document uses only standard packages: `geometry`, `enumitem`, `titlesec`, `xcolor`, `hyperref`, `babel` (brazil), and `charter`. No external fonts or custom classes are required.

## License

This project is proprietary. All rights reserved.
