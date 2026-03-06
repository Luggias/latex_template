# 📄 LaTeX University Summary Template

> A professional, ready-to-use LaTeX template for university summaries including a custom style, smart VSCode snippets, intuitive keyboard shortcuts, and a convenient build pipeline. Designed for students who want professional, well-formatted, consistent notes without fighting the tooling. 	A game-changer for every STEM student aiming for perfectly organized, high-quality notes.

[![License: Apache License](https://img.shields.io/badge/License-Apache_2.0-yellow.svg)](https://opensource.org/licenses/Apache-2.0)
[![Made with LaTeX](https://img.shields.io/badge/Made%20with-LaTeX-1f425f.svg)](https://www.latex-project.org/)
[![VSCode](https://img.shields.io/badge/Editor-VSCode-blue.svg)](https://code.visualstudio.com/)

**Author:** Lukas Kapferer | [lukas-kapferer.com](https://lukas-kapferer.com) | [github.com/Luggias](https://github.com/Luggias)

---

## Table of Contents

1. [What is this?](#what-is-this)
2. [Features](#features)
3. [Folder Structure](#folder-structure)
4. [Setup](#setup)
   - [macOS](#macos)
   - [Windows](#windows)
   - [Overleaf](#overleaf)
5. [VSCode Configuration](#vscode-configuration)
   - [settings.json](#settingsjson)
   - [Snippets (latex.json)](#snippets-latexjson)
   - [Keyboard Shortcuts (keybindings.json)](#keyboard-shortcuts-keybindingsjson)
6. [Working with the Template](#working-with-the-template)
7. [HSG vs. General Template](#hsg-vs-general-template)
8. [LaTeX Resources](#latex-resources)

---

## What is this?

[LaTeX](https://www.latex-project.org/) is a professional typesetting system widely used in academia, science, and engineering. Unlike Word, it separates *content* from *formatting* — you write plain text with markup, and LaTeX compiles it into a beautifully typeset PDF. The learning curve is real, but the results are unmatched.

This repository gives you a **complete, pre-configured LaTeX environment** so you can skip the painful setup and go straight to writing. It includes a polished custom style, a curated set of VSCode snippets for the most common LaTeX constructs, keyboard shortcuts that mirror what you already know (bold with `Cmd+B`, italic with `Cmd+I`), and a build pipeline that compiles and cleans automatically on save.

There are two template variants: one **general template** for any university, and one **HSG-specific variant** with the University of St.Gallen (HSG) logo and name pre-filled on the title page.

---

## Features

- **Custom style file** (`mystyle.sty`) — consistent typography, spacing, colour boxes, code blocks, and a custom fourth heading level (`\subsubsubsection`) out of the box
- **Smart snippets** — trigger complex LaTeX environments with 2–5 keystrokes (tables, figures, code blocks, colour boxes, and more)
- **Keyboard shortcuts** — formatting shortcuts that feel native (`Cmd/Ctrl+B` for bold, `Cmd/Ctrl+I` for italic, `Cmd/Ctrl+1–4` for headings)
- **Auto-build + auto-clean** — the PDF rebuilds on every save and auxiliary files are cleaned up automatically
- **SyncTeX support** — click in the PDF to jump to the source, or click in the source to jump to the PDF
- **HSG variant** — dedicated template with HSG branding for University of St. Gallen students
- **Bibliography support** — pre-configured for academic citations
- **ChkTeX linting** — catches common LaTeX mistakes as you type, with a sensible `.chktexrc` suppressing false positives

---

## Folder Structure

```
LATEX_TEMPLATE/
│
├── latex_HSG_summary_template/        # HSG-specific variant (see below)
│   ├── bib/                           # Bibliography source files (.bib)
│   ├── content/
│   │   ├── bibliography.tex           # Renders the bibliography section
│   │   ├── figures_list.tex           # Renders the list of figures
│   │   └── main_content.tex           # ← YOUR CONTENT GOES HERE
│   ├── fig/                           # All images, screenshots, PDFs for figures
│   ├── styles/
│   │   └── mystyle.sty                # Custom style — do not edit unless you know what you're doing
│   ├── .chktexrc                      # ChkTeX linter configuration — do not delete
│   ├── latex_HSG_summary_template.tex # Main entry point — rename this per subject
│   └── latex_HSG_summary_template.synctex.gz  # Build output — safe to ignore
│
├── latex_summary_template/            # General variant (identical structure, no HSG branding)
│
└── vscode_settings_template/          # VSCode configuration files
    ├── keybindings.json               # Custom keyboard shortcuts
    ├── latex.json                     # Custom snippets
    ├── settings.json                  # LaTeX Workshop and editor settings
    └── README.md
```

### What each file and folder does

**`content/main_content.tex`** — This is where you write all your notes. You never need to touch any other content file for day-to-day writing.

**`content/bibliography.tex`** — Renders the bibliography at the end of your document. It pulls entries from the `.bib` files inside `bib/`. You only need this if you are citing sources.

**`content/figures_list.tex`** — Renders a List of Figures section. Useful for longer summaries with many diagrams. Can be toggled on/off in the main `.tex` file.

**`bib/`** — Place your `.bib` bibliography files here. These contain your citation entries in BibTeX format. Export them directly from Zotero, Mendeley, or Google Scholar.

**`fig/`** — Place all images, screenshots, and PDFs you want to include as figures here. The `image` snippet references this folder automatically.

**`styles/mystyle.sty`** — The custom style file that defines the visual look of the document, imports all packages, configures code block colours, defines the custom fourth heading level, and more. You generally do not need to edit this.

**`latex_HSG_summary_template.tex`** (or `latex_summary_template.tex`) — The main entry point of the document. Here you can configure the page geometry, author, title, date, PDF metadata, and toggle the table of contents, list of figures, list of tables, and bibliography on or off.

**`.chktexrc`** — Configuration file for the ChkTeX linter. It suppresses specific warnings that are triggered by valid constructs in this template (e.g. warnings about `\(` inline math). **Do not delete this file** — without it, you will see a flood of false-positive warnings in your editor.

**`*.synctex.gz`** — A binary file generated during compilation that enables SyncTeX (click-to-navigate between source and PDF). It is a build artefact and can be safely ignored. It does not appear in the compiled PDF.

---

## Setup

### macOS

#### 1. Install Homebrew (optional but recommended)

Homebrew is a package manager for macOS. While not strictly required for this template, it makes managing developer tools much easier.

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### 2. Install MacTeX

MacTeX is the full LaTeX distribution for macOS. Download and install it from the official website:

👉 [https://www.tug.org/mactex/](https://www.tug.org/mactex/)

The download is large (~5 GB). Install it like any standard macOS `.pkg` installer.

#### 3. Install Visual Studio Code

Download VSCode from [https://code.visualstudio.com](https://code.visualstudio.com) and install it.

#### 4. Install the LaTeX Workshop Extension

Open VSCode, go to the Extensions panel (`Cmd+Shift+X`), search for **LaTeX Workshop** by James Yu, and install it. This extension provides PDF preview, auto-build, SyncTeX, linting, and IntelliSense for LaTeX.

#### 5. Install the LaTeX Utilities Extension (optional — for word count)

While in the Extensions panel, also search for **LaTeX Utilities** by tecosaur and install it. This adds a live word count indicator to the status bar at the bottom of VSCode.

#### 6. Configure Snippets

Press `Cmd+Shift+P`, type **Snippets: Configure Snippets**, press Enter, then search for and select **latex**. This opens your `latex.json` snippets file. Copy the entire content from `vscode_settings_template/latex.json` in this repository and paste it into that file (replacing any existing content).

#### 7. Configure Settings

Press `Cmd+Shift+P`, type **Preferences: Open User Settings (JSON)**, and press Enter. This opens your `settings.json`. Append the content from `vscode_settings_template/settings.json` into this file. Be careful to maintain valid JSON — if your file already has content, merge the keys rather than duplicating the outer `{}` braces.

#### 8. Configure Keyboard Shortcuts

Press `Cmd+Shift+P`, type **Preferences: Open Keyboard Shortcuts (JSON)**, and press Enter. Copy the entire content from `vscode_settings_template/keybindings.json` and paste it into that file.

#### 9. Restart VSCode

Fully quit and reopen VSCode (`Cmd+Q`, then relaunch) for all settings to take effect.

---

### Windows

#### 1. Install MiKTeX or TeX Live

There are two major LaTeX distributions for Windows. **MiKTeX** is recommended for beginners because it installs missing packages on demand.

- MiKTeX: [https://miktex.org/download](https://miktex.org/download)
- TeX Live (full, larger): [https://www.tug.org/texlive/](https://www.tug.org/texlive/)

Download and run the installer. During setup, allow MiKTeX to install missing packages automatically when prompted.

#### 2. Install Visual Studio Code

Download VSCode from [https://code.visualstudio.com](https://code.visualstudio.com) and install it.

#### 3. Install the LaTeX Workshop Extension

Open VSCode, go to the Extensions panel (`Ctrl+Shift+X`), search for **LaTeX Workshop** by James Yu, and install it.

#### 4. Install the LaTeX Utilities Extension (optional — for word count)

Search for **LaTeX Utilities** by tecosaur and install it.

#### 5. Configure Snippets

Press `Ctrl+Shift+P`, type **Snippets: Configure Snippets**, press Enter, then search for **latex**. Copy the content from `vscode_settings_template/latex.json` and paste it into the opened file.

#### 6. Configure Settings

Press `Ctrl+Shift+P`, type **Preferences: Open User Settings (JSON)**, and press Enter. Append the content from `vscode_settings_template/settings.json`.

> **Note for Windows users:** The `settings.json` in this repository contains a macOS-specific path for ChkTeX (`/Library/TeX/texbin/chktex`). On Windows, remove or update this line:
> ```json
> "latex-workshop.linting.chktex.exec.path": "/Library/TeX/texbin/chktex"
> ```
> With MiKTeX, ChkTeX should be on your PATH automatically and this line can simply be deleted.

#### 7. Configure Keyboard Shortcuts

Press `Ctrl+Shift+P`, type **Preferences: Open Keyboard Shortcuts (JSON)**, and press Enter. Copy the content from `vscode_settings_template/keybindings.json` and paste it into that file.

#### 8. Restart VSCode

Fully close and reopen VSCode for all settings to take effect.

---

### Overleaf

[Overleaf](https://www.overleaf.com) is a browser-based LaTeX editor that requires no local installation. It is a great option if you do not want to install anything on your machine.

**To use this template on Overleaf:**

1. Download this repository as a `.zip` file (click **Code → Download ZIP** on GitHub).
2. Log in to Overleaf and click **New Project → Upload Project**.
3. Upload the `.zip` file.
4. Set the main document to `latex_summary_template.tex` (or the HSG variant) in the project settings.

> **Note:** The VSCode snippets and keyboard shortcuts do not apply in Overleaf. The template itself (style, structure, content files) works fully. Overleaf has its own snippet and autocomplete system.

---

## VSCode Configuration

### settings.json

This file configures the LaTeX Workshop extension and general editor behaviour. The key settings are:

| Setting | Value | What it does |
|---|---|---|
| `latex-workshop.view.pdf.viewer` | `"tab"` | Opens the compiled PDF in a VSCode tab rather than an external viewer, enabling split-screen mode |
| `files.autoSave` | `"onFocusChange"` | Automatically saves the file when you click away, which triggers a build |
| `latex-workshop.latex.autoBuild.run` | `"onSave"` | Triggers a full PDF build every time the file is saved |
| `latex-workshop.latex.autoBuild.cleanAndRetry.enabled` | `true` | If a build fails, cleans auxiliary files and retries automatically |
| `latex-workshop.linting.chktex.enabled` | `true` | Enables the ChkTeX linter to highlight potential issues as you type |
| `latex-workshop.latex.recipe.default` | `"build → clean"` | After every build, automatically cleans up auxiliary files (`.aux`, `.log`, etc.) |

**Build recipes** — the settings define three named build recipes you can invoke manually from the LaTeX Workshop sidebar:

- **`build → clean`** *(default)*: Compiles with `latexmk` using `shell-escape` and `-synctex=1`, then cleans auxiliary files.
- **`only build`**: Compiles without cleaning. Useful when debugging build errors.
- **`only clean`**: Cleans auxiliary files without compiling. Useful when the project is in a broken state.

The `-shell-escape` flag is required by the `minted` package (used for syntax-highlighted code blocks). The `-synctex=1` flag enables click-to-navigate between the PDF and source.

---

### Snippets (latex.json)

Snippets are triggered by typing a short prefix and pressing `Tab`. Many snippets use **tab stops** (`$1`, `$2`, ...) — after inserting the snippet, press `Tab` to jump between the editable fields in order.

Where noted, snippets also support **selected text** — select some text first, then trigger the snippet, and the selected text will be placed inside the inserted construct automatically.

| Prefix | Description | Tab Stops |
|---|---|---|
| `itemize` | Bullet point list (`\begin{itemize}`) | 1: first item |
| `enumerate` | Numbered list (`\begin{enumerate}`) | 1: first item |
| `java` | Java code block using the `listings` package | 1: code content |
| `python` | Python code block using the `listings` package | 1: code content |
| `table` | 3-column professional table with `\toprule`, `\midrule`, `\bottomrule` (booktabs style), commented-out caption and label | 1–3: headers; 4–12: 3×3 cell content; 13: caption; 14: label |
| `image` | Figure environment with `\includegraphics`, commented-out caption and label, pre-pointed at the `fig/` folder | 1: width fraction; 2: filename; 3: caption; 4: label |
| `ccode` | Inline code using `\code\|...\|` | 1: code content |
| `ttext` | Monospaced text using `\texttt{}` | 1: text |
| `lline` | Horizontal rule with vertical spacing above and below | 1: top spacing (default `0.4cm`); 2: bottom spacing (default `0.4cm`) |
| `bbox` | Colour box using `tcolorbox` with dropdown colour picker for background and frame, title, and optional caption/label | 1: background colour; 2: frame colour; 3: title; 4: caption; 5: label; 6: content |
| `vspace-0.2` | Vertical space of 0.2 cm | 1: value (editable) |
| `vspace-0.5` | Vertical space of 0.5 cm | 1: value (editable) |
| `vspace-1` | Vertical space of 1 cm | 1: value (editable) |
| `vspace-1.5` | Vertical space of 1.5 cm | 1: value (editable) |
| `vspace-2` | Vertical space of 2 cm | 1: value (editable) |
| `minipage` | Single minipage environment with adjustable width | 1: width fraction (default `0.49`); 2: content |
| `miniside` | Two minipages side by side with `\hfill` between them | 1: left width; 2: left content; 3: right width; 4: right content |
| `ccolour` | Coloured text using `\textcolor{}{}` | 1: colour name; 2: text |

> **Tip:** The `table` snippet pre-fills proportional column widths that sum to 0.92 (a safe margin for three-column layouts). You can adjust the `p{...}` values to change column ratios.

> **Tip:** The `bbox` snippet uses a dropdown for colours — when the snippet is inserted, VSCode will show a choice list for the background and frame colour. Use arrow keys to select.

---

### Keyboard Shortcuts (keybindings.json)

All shortcuts are **context-aware** — they only activate when a `.tex` file is open and focused. This means they will not interfere with your shortcuts in other file types or applications.

Shortcuts that act on **selected text** will wrap the selection in the corresponding command. If nothing is selected, they insert the command with a tab stop inside.

#### Text Formatting

| Shortcut (Mac) | Shortcut (Windows) | Action | LaTeX Output |
|---|---|---|---|
| `Cmd+B` | `Ctrl+B` | **Bold** | `\textbf{...}` |
| `Cmd+I` | `Ctrl+I` | *Italic* | `\textit{...}` |
| `Cmd+U` | `Ctrl+U` | Underline | `\underline{...}` |
| `Cmd+E` | `Ctrl+E` | Enquote (smart quotes) | `\enquote{...}` |

#### Headings

| Shortcut (Mac) | Shortcut (Windows) | Action |
|---|---|---|
| `Cmd+1` | `Ctrl+1` | Insert `\section{}` with decorative comment separators |
| `Cmd+2` | `Ctrl+2` | Insert `\subsection{}` |
| `Cmd+3` | `Ctrl+3` | Insert `\subsubsection{}` |
| `Cmd+4` | `Ctrl+4` | Insert `\subsubsubsection{}` *(custom 4th level heading defined in `mystyle.sty`)* |

> **Tip:** All heading shortcuts support selected text. Highlight a line of text and press `Cmd+1` to instantly wrap it in `\section{}`.

#### Other

| Shortcut (Mac) | Shortcut (Windows) | Action | LaTeX Output |
|---|---|---|---|
| `Cmd+R` | `Ctrl+R` | Right arrow symbol | `\(\rightarrow\)` |
| `Cmd+Y` | — | Redo *(remapped from `Shift+Cmd+Z`)* | — |

---

## Working with the Template

### Starting a new subject

1. Copy the `latex_summary_template` folder (or `latex_HSG_summary_template` if you are at HSG) and rename it to your subject name.
2. Rename the main `.tex` file (e.g. `latex_summary_template.tex` → `microeconomics.tex`). The compiled PDF will take the same name as this file.
3. Open the renamed folder in VSCode.

### Day-to-day workflow

- **All your writing goes in `content/main_content.tex`**. You do not need to rename or touch any other file for normal note-taking.
- Open the main `.tex` file and save it (`Cmd+S` / `Ctrl+S`). VSCode will automatically compile the PDF and place it in the same folder.
- **Split-screen mode:** Drag the PDF tab to the right side of the screen to work in split view alongside your source file. This lets you see changes in real time.
- **SyncTeX — forward search:** Click somewhere in the PDF while holding `Cmd` (Mac) or `Ctrl` (Windows) to jump to the corresponding line in the source.
- **SyncTeX — inverse search:** In the LaTeX Workshop sidebar, use the "SyncTeX from cursor" button (or the shortcut) to jump from the source to the corresponding position in the PDF.

### Configuring the document

Open your main `.tex` file to adjust document-level settings:

- **Page geometry** — margins, paper size
- **Author, title, date** — shown on the title page
- **PDF metadata** — title, author, subject (used by PDF readers and screen readers) via `\hypersetup`
- **Toggle sections** — comment/uncomment `\tableofcontents`, `\listoffigures`, `\listoftables`, and the bibliography include to enable or disable them

### Word count

If you installed the **LaTeX Utilities** extension, a live word count appears in the VSCode status bar at the bottom of the screen while you have a `.tex` file open.

### Yellow warnings in the editor

ChkTeX may underline some constructs in yellow. These are **linting warnings**, not errors — they do not prevent the PDF from compiling. The `.chktexrc` file suppresses the most common false positives for this template's style. Any remaining yellow marks are safe to ignore unless you see a genuine typo or structural issue.

### Understanding the output files

After compilation, you will see several files alongside your `.tex` file:

- **`.pdf`** — your compiled document
- **`.synctex.gz`** — enables click-to-navigate between source and PDF; do not delete it while working, but safe to ignore otherwise
- Other auxiliary files (`.aux`, `.log`, `.toc`, etc.) — these are cleaned automatically by the default build recipe and will not normally appear

---

## HSG vs. General Template

| | `latex_HSG_summary_template` | `latex_summary_template` |
|---|---|---|
| University logo on title page | ✅ HSG logo pre-filled | ❌ |
| University name on title page | ✅ "University of St.Gallen (HSG)" | ❌ |
| Style file (`mystyle.sty`) | ✅ Identical | ✅ Identical |
| Content structure | ✅ Identical | ✅ Identical |

**If you are an HSG student:** use `latex_HSG_summary_template`. Feel free to delete the `latex_summary_template` folder.

**If you are at any other university:** use `latex_summary_template`. Feel free to delete the `latex_HSG_summary_template` folder. You can add your own university logo by replacing the `university-logo.png` file inside of the `fig` folder while preserving its name.

---

## LaTeX Resources

New to LaTeX? These are the best places to get started:

- 📺 [LaTeX Tutorial (Derek Banas)](https://www.youtube.com/watch?v=lgiCpA4zzGU) — a solid single-video introduction
- 📺 [LaTeX Tutorial Playlist (Dr. Trefor Bazett)](https://www.youtube.com/playlist?list=PLHXZ9OQGMqxcWWkx2DMnQmj5os2X5ZR73) — comprehensive series covering most use cases
- 📖 [Learn LaTeX in 30 Minutes (Overleaf)](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes) — excellent written guide from the Overleaf team

---

## License

This project is licensed under the Apache License. See [LICENSE](LICENSE) for details.

---

*Made with <3 by [Lukas Kapferer](https://lukas-kapferer.com)*