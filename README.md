# Merit Aid, Sorting, and Institutional Access: Evidence from Tennessee's HOPE Scholarship

**Balint Kidd, Tommy Soltanian, Tyler Sotomayor, Gabriel Uceda-Sosa**
Columbia University | April 2026

Presented at the [2026 Economic Scholars Program](https://www.clevelandfed.org/events/economic-scholars-program), Federal Reserve Bank of Cleveland

---

## Abstract

Merit-based scholarship programs are widely viewed as regressive because eligibility correlates with family income. We show that this conclusion conflates individual attendance effects with institutional composition effects — distinct estimands that can move in opposite directions when students sort across multiple sectors. Using tax-linked data from Chetty et al. (2020), we find that Tennessee's HOPE Scholarship reshapes the full parental income distribution at public colleges: all five income quintiles shift monotonically, with bottom-quintile share rising and top-quintile share falling. A three-destination sorting framework reconciles these progressive composition effects with the regressive attendance findings of Dynarski (2000) and identifies program design parameters that determine sorting direction.

---

## Repository Structure

```
merit-aid-working-paper/
├── main.tex                  # Master document (preamble + \input calls)
├── references.bib            # Bibliography (APA style, biblatex + biber)
├── .gitignore                # Excludes LaTeX build artifacts
├── sections/
│   ├── frontmatter.tex       # Title, authors, abstract, JEL codes, keywords
│   ├── introduction.tex      # Section 1
│   ├── background.tex        # Section 2: Institutional background
│   ├── theory.tex            # Section 3: Three-destination sorting model
│   ├── data.tex              # Section 4: Data and sample construction
│   ├── empirical_strategy.tex # Section 5: Identification and inference
│   ├── results.tex           # Section 6: Main results and mechanisms
│   ├── robustness.tex        # Section 7: Robustness checks
│   ├── discussion.tex        # Section 8: Cross-state evidence and extensions
│   ├── conclusion.tex        # Section 9
│   ├── figures.tex           # Appendix A: Figures
│   └── tables.tex            # Appendix B: Tables
├── figures/                  # Paper-ready PDF figures (22 files)
├── tables/                   # LaTeX table inputs (5 files)
└── tikz/                     # TikZ diagram sources
    └── fig_sorting_model.tex
```

## Compiling

Requires a LaTeX distribution with `pdflatex` and `biber` (e.g., TeX Live, MiKTeX).

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

Or with `latexmk`:

```bash
latexmk -pdf main.tex
```

## Two-Repo Sync Workflow

This repository is the **paper-only** repo linked to Overleaf. The full research project (code, data, revision tracking) lives in a separate repo: [`merit-aid-sprint03`](https://github.com/tylersotomayor/merit-aid-sprint03).

### Repositories

| Repo | Contains | Linked to |
|------|----------|-----------|
| `merit-aid-working-paper` (this repo) | .tex, figures, tables, compiled PDF | Overleaf |
| `merit-aid-sprint03` | Everything: code, data, paper, revision tracking | Claude Code |

### Sync Flow

Both directions follow the same pattern: **Pull -- Edit -- Push -- other side Pulls.**

**Editing in Overleaf (you/coauthors):**
```
Overleaf --> Push to merit-aid-working-paper (GitHub button in Overleaf)
         --> At next Claude Code session, pull into sprint_03/paper/
```

**Editing via Claude Code (revision sessions):**
```
sprint_03/paper/ --> push to merit-aid-sprint03
                 --> copy files to merit-aid-working-paper, push
                 --> Pull into Overleaf (GitHub button in Overleaf)
```

### Rules

1. **Always pull before pushing** from either direction to avoid overwriting the other's edits.
2. **During active revision sessions**, edits flow one way: Claude Code --> GitHub --> Overleaf. Avoid editing in Overleaf during these sessions.
3. **Between sessions**, Overleaf edits are fine — they'll be synced into sprint_03 at the start of the next session.

### Overleaf Sync Actions

| Action | How |
|--------|-----|
| **Pull GitHub changes into Overleaf** | Overleaf sidebar > GitHub > Pull GitHub changes into Overleaf |
| **Push Overleaf edits to GitHub** | Overleaf sidebar > GitHub > Push Overleaf changes to GitHub |

## Contributing

1. Edit individual section files in `sections/`, not `main.tex`
2. Compile to check for errors
3. Commit with the `paper:` prefix (e.g., `paper: update results section`)
4. Push to GitHub; pull in Overleaf

## License

This is an unpublished working paper. All rights reserved by the authors.
