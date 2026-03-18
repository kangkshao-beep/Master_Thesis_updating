# Repository Guidelines

## Project Structure & Module Organization
- Main entry `template.tex` includes sections from `introduction.tex`, `Standard_Model.tex`, `Theoretical_Study_on_Semi-leptonic_Decay.tex`, `appendix_A.tex`, and `Summary.tex`.
- Bibliography lives in `bib/database.bib` with style `bib/lzubib.bst`; adjust citations via `\cite`/`\ct`.
- Class and formatting are defined in `LZUThesis-PgD&PhD.cls`; avoid editing unless template updates are required.
- Figures reside in `figures/`; keep new assets there and reference with `\includegraphics{figures/<name>}`.
- Generated artifacts (`*.aux`, `*.log`, `*.out`, `*.bbl`, `*.blg`, `*.synctex.gz`, `*.lof`, `*.lot`) should be cleaned before committing.

## Build, Test, and Development Commands
- `xelatex template.tex` → compile; run twice to resolve refs.
- `bibtex template` → generate bibliography after the first compile.
- Repeat `xelatex template.tex` twice post-bibtex for stable refs; `open template.pdf` to review output.
- If available, `latexmk -pdf -xelatex template.tex` automates the full cycle; `latexmk -pvc -pdf -xelatex template.tex` for continuous preview; `latexmk -c template.tex` cleans intermediates.

## Coding Style & Naming Conventions
- Use UTF-8 XeLaTeX; keep macros consistent with those in `template.tex` (e.g., `\GeV`, `\tb`); prefer `\ref`/`\label` pairs for figures, tables, and equations.
- Place new figures in `figures/` with descriptive lowercase names using hyphens or underscores; embed via relative paths only.
- Keep section files focused: math in display mode, equations numbered when referenced, minimal package additions (justify any new package in comments).

## Testing Guidelines
- After content changes, ensure a clean build (`xelatex` → `bibtex` → `xelatex` ×2) with no `Undefined` or `Overfull` warnings in `template.log`.
- Check that new citations appear in `template.bbl` and hyperlinks resolve correctly in `template.pdf`.
- Verify figure/table placement and page breaks; adjust floats (`[htbp]`) or `\clearpage` sparingly.

## Commit & Pull Request Guidelines
- Use concise, imperative commit messages (e.g., `Add charm decay spectrum figure`, `Clarify HQET expansion details`).
- For reviews, include: summary of sections touched, build command used and whether warnings remain, list of new figures/bibliography entries, and updated `template.pdf` when visual changes occur.
- Avoid committing generated files; keep the repo clean by running `latexmk -c template.tex` before pushing.
