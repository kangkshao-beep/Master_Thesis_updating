# v0.1 — Thesis Source Archive and Reproducibility Baseline

This first public release archives the LaTeX source of my master's thesis project on inclusive charm semileptonic decays and establishes a reproducibility baseline for future maintenance.

## Main contents

- Thesis LaTeX source files
- Bibliography and figure assets
- Existing compiled PDF snapshot
- Initial `AGENTS.md` instructions for AI-assisted maintenance and review
- `CITATION.cff` metadata for repository citation
- GitHub Actions workflow for XeLaTeX build checks

## Scientific scope

- Inclusive charm semileptonic decays
- HQET/OPE-based theoretical framework
- Heavy-quark mass-scheme considerations
- Lepton-energy spectra and phenomenological observables
- Reproducible scientific writing and source preservation

## Reproducibility notes

The main LaTeX entry point is `template.tex`. The repository is designed to build with XeLaTeX and BibTeX. The GitHub Actions workflow uses a CI-specific temporary file, `template-ci.tex`, to replace macOS-specific Chinese font names with Linux-compatible Noto CJK fonts during automated builds.

## Future maintenance plans

- Improve README and repository-level documentation
- Clean generated auxiliary files from version control where appropriate
- Add issue templates for build and reproducibility problems
- Add future Mathematica/Python validation scripts if they become part of the public workflow
- Prepare more structured release notes for later research-code updates
