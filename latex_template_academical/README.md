# Trading Handbook (LaTeX)

A 300‑page, English‑language handbook that takes you from the microstructure
of limit‑order books all the way to Python‑based algorithmic trading.

*Author & maintainer — \<Lukas Kapferer\>*  
*License — MIT (code) / CC‑BY‑SA 4.0 (text)*

---

## 📂 Directory Structure

├── main.tex # Root file – orchestration only
├── mystyle.sty # Reusable style sheet (packages, macros, fonts)
├── content/ # One sub‑folder per part
│   ├── part1/
│   │   ├── 01_Market_Microstructure.tex
│   │   └── …
│   ├── part2/
│   └── … (parts 3 – 6)
├── fig/ # PDF/SVG figures generated externally
├── code/ # Python scripts / notebooks
├── data/ # Sample CSV / Parquet files
├── biblio/
│   └── trading.bib # BibLaTeX database
├── .latexmkrc # Build helper (shell‑escape, -pvc config)
└── README.md # You are here


<details>
<summary>Why <code>content/</code> instead of <code>chapters/</code>?</summary>

You can adopt either name—just keep `\include{…}` paths in `main.tex`
consistent.  
The handbook currently expects `content/partX/...`.
</details>

---

## 🔧 Build Instructions

1. **Prerequisites**
   * TeX Live 2024+ or MiKTeX 22+
   * Python ≥ 3.9 with the `Pygments` package (for `minted`)
   * `biber` 2.18+ Bibliography backend (BibLaTeX) (modern replacement for `bibtex`)
   * Pygments Version: latest (for `Syntax` highlighting)
   * (optional) `latexmk` | ships with TeX Live | One‑command build / watch |

2. **Compile**
   ```bash
   latexmk -pdf -shell-escape main.tex
   
   On Overleaf:
    Settings → Compiler = pdfLaTeX
    Settings → Shell Escape = Enabled
    
3. **Continuous Build**
   latexmk -pvc watches for changes and recompiles automatically.