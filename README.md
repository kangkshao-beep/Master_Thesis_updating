# Inclusive Charm Semileptonic Decays — Thesis Source and Reproducibility Notes

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![TeX](https://img.shields.io/badge/source-LaTeX-blue)
![Status](https://img.shields.io/badge/status-reproducibility%20baseline-lightgrey)

This repository contains the LaTeX source, bibliography, figures, and supporting materials for my master's thesis project on **inclusive charm semileptonic decays**. It is being maintained as an open research artifact for reproducible scientific writing and future AI-assisted review of theoretical-particle-physics calculations.

The current repository should be read primarily as a **thesis-source archive and reproducibility baseline**, not yet as a polished numerical-code package.

## Scientific Scope

The project focuses on theoretical and phenomenological aspects of inclusive semileptonic charm decays, with emphasis on topics such as

* inclusive charm semileptonic decay processes;
* heavy-quark expansion and operator product expansion ideas;
* heavy-quark mass-scheme considerations;
* lepton-energy spectra and related phenomenological observables;
* source-level preservation of a thesis-style research workflow.

The long-term goal is to make the repository useful not only as a static thesis archive, but also as a maintainable open-research project where formulas, references, figures, and build outputs can be checked reproducibly.

## Repository Structure

```text
.
├── template.tex                         # Main LaTeX entry point
├── introduction.tex                     # Introduction section
├── Standard_Model.tex                   # Standard Model background
├── Theoretical_Study_on_Semi-leptonic_Decay.tex
├── mass_scheme.tex                      # Heavy-quark mass-scheme discussion
├── system_engineering.tex               # Systematic/engineering-related material
├── Data_Analysis_Phenomenonology.tex    # Data analysis and phenomenology notes
├── Question.tex                         # Supplementary notes/questions
├── Summary.tex                          # Summary section
├── appendix_A.tex
├── appendix_B.tex
├── bib/
│   ├── database.bib                     # Bibliography database
│   └── lzubib.bst                       # Bibliography style
├── figures/                            # Figure assets used by the thesis
├── LZUThesis-PgD&PhD.cls                # Thesis class file
├── AGENTS.md                           # Instructions for AI-assisted maintenance
├── LICENSE                             # MIT license
└── README.md
```

The main compilation target is `template.tex`.

## Build Requirements

A working LaTeX distribution with XeLaTeX and BibTeX is required. Recommended choices are

* TeX Live on Linux;
* MacTeX on macOS;
* an equivalent LaTeX environment with Chinese-font support.

The project uses XeLaTeX, so plain `pdflatex` is not the intended build engine.

## Build Instructions

A full manual build can be performed with

```bash
xelatex template.tex
bibtex template
xelatex template.tex
xelatex template.tex
```

If `latexmk` is available, the recommended command is

```bash
latexmk -pdf -xelatex template.tex
```

For continuous preview during editing, use

```bash
latexmk -pvc -pdf -xelatex template.tex
```

To clean intermediate build files, use

```bash
latexmk -c template.tex
```

Before committing changes, please make sure the project builds cleanly and that the final PDF has no unresolved references or missing citations.

## Reproducibility Checks

After modifying the thesis source, check the following items:

1. `template.tex` compiles successfully with XeLaTeX.
2. Bibliography entries resolve correctly after running BibTeX.
3. Cross references, equation references, figure references, and table references are not broken.
4. Figures are loaded from relative paths, preferably under `figures/`.
5. Generated auxiliary files are not committed unless there is a specific reason.
6. The compiled PDF is visually inspected for major layout problems.

Useful log checks include searching `template.log` for

```text
Undefined
Citation
Reference
Overfull
Missing
```

Some `Overfull` warnings may be harmless in thesis-style LaTeX projects, but new warnings should still be reviewed.

## AI-Assisted Maintenance

This repository includes an `AGENTS.md` file to guide AI-assisted review and maintenance. AI tools such as Codex can be used for tasks including

* checking LaTeX build consistency;
* reviewing pull requests and diffs;
* detecting broken labels, references, and citations;
* cleaning generated files from commits;
* improving repository documentation;
* preparing release notes;
* organizing future symbolic or numerical validation scripts.

AI-generated changes should always be reviewed by a human maintainer, especially when they touch physics formulas, numerical inputs, bibliography entries, or thesis-specific formatting.

## Roadmap

Planned maintenance work includes

* [x] improve repository-level documentation;
* [x] add `CITATION.cff`;
* [x] add GitHub Actions for automated LaTeX build checks;
* [x] create a first versioned release, e.g. `v0.1-thesis-source`;
* [x] clean generated auxiliary files from version control where appropriate;
* [x] add issue templates for build problems and reproducibility problems;
* [x] organize future Mathematica/Python validation scripts if they become part of the public workflow.

## Citation

If this repository is useful for your research, teaching, or reproducibility workflow, please cite the repository or the associated thesis. Citation metadata is provided in `CITATION.cff`.

A provisional BibTeX entry is

```bibtex
@misc{shao_master_thesis_updating,
  author       = {Shao, KangKang},
  title        = {Inclusive Charm Semileptonic Decays: Thesis Source and Reproducibility Notes},
  year         = {2025},
  howpublished = {\url{https://github.com/kangkshao-beep/Master_Thesis_updating}},
  note         = {Thesis source archive and reproducibility baseline}
}
```

## License

This repository is released under the MIT License. See [`LICENSE`](LICENSE) for details.

## Maintainer Notes

This repository is currently maintained as a focused open-research artifact. Contributions, issue reports, and reproducibility suggestions are welcome, but all scientific changes should preserve the original thesis context unless explicitly marked as later updates.
