# ktheory
This is my repository for my Master's Project A in the semester of Aug-Nov 2026 on "Higher Algebraic K-Theory", which hosts LaTeX source code for a thesis introducing higher algebraic K-theory, including the passage from the classical K-groups K₀, K₁ and K₂ of a ring to the higher groups Kₙ, and the main tools used to define and compute them.

**Author:** Naveen Maurya

# Abstract
Algebraic $K$-theory associates to a ring $R$ a sequence of abelian groups
$K_n(R)$ encoding its finitely generated projective modules, in analogy with
the topological $K$-theory of vector bundles. This thesis gives an
introduction to the subject, from the classical low-degree groups to
Quillen's definition of the higher groups.

We begin with projective modules and Swan's theorem, then construct the
Grothendieck group $K_0$ for rings, symmetric monoidal categories and exact
categories. Next we study the classical groups $K_1(R) = GL(R)/E(R)$ and
$K_2(R)$.

After reviewing the required homotopy theory, including classifying spaces of
categories, $H$-spaces, Quillen's Theorems A and B, and the $+$-construction,
we define the higher groups $K_n(R)$ in three ways: through the
$BGL(R)^+$ construction, the $S^{-1}S$ construction, and Quillen's
$Q$-construction. We show that these agree with the classical groups in low
degrees and with each other, culminating in the ``$+ = Q$'' theorem.


## Repository layout

```
ktheory/
├── main.tex          # Root document (adjust if your entry file is named differently)
├── references.bib    # Bibliography database (biblatex)
├── content/          # One .tex file per chapter
| ├── chapter1.tex    # Preliminaries
| ├── chapter2.tex    # The Grothendieck Group K_0
| ├── chapter3.tex    # Groups K_1 and K_2 of a ring
| ├── chapter4.tex    # Homotopy Theory Preliminaries
| └── chapter5.tex    # Higher K-Theory and the K_n Groups
└── README.md
```

## Building

The bibliography uses **biblatex with the biber backend**, so a plain `pdflatex` run is not enough. The standard sequence is:

```bash
pdflatex main
biber main
pdflatex main
pdflatex main
```

Or let `latexmk` handle all the passes:

```bash
latexmk -pdf main.tex
```

Clean up auxiliary files with:

```bash
latexmk -C
```

### Requirements

- A recent TeX distribution (TeX Live, MiKTeX or MacTeX)
- `biber` (ships with the distributions above)
- Standard packages: `amsmath`, `amssymb`, `amsthm`, `biblatex`, `hyperref`, plus any listed in the preamble of `main.tex`

### Troubleshooting

- **Citations show as `[?]`:** run `biber` after the first `pdflatex` pass, then `pdflatex` twice more.
- **`biber` version mismatch error:** your `biber` and `biblatex` versions must match; update both from your TeX distribution.
- **Stale page numbers or table of contents:** delete the `.aux`, `.toc` and `.bbl` files and rebuild.

## Bibliography

References are kept in `references.bib` and rendered with biblatex. To add a source, append a BibTeX entry to that file and cite it with `\cite{key}` or `\textcite{key}`.
