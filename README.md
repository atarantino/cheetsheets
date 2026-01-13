# LaTeX Cheat Sheets

A collection of LaTeX-based cheat sheets for productivity tools and shortcuts.

## Available Cheat Sheets

- [macOS Productivity Cheat Sheet](build/productivity-cheatsheet-mac.pdf)
- [Windows Productivity Cheat Sheet](build/productivity-cheatsheet-windows.pdf)
- [Vim Cheat Sheet](build/vim_cheat_sheet.pdf)
- [Cursor Cheat Sheet](build/cursor-cheatsheet.pdf)

## Prerequisites

Install a LaTeX distribution and ensure `latexmk` is available:
- Linux: TeX Live (e.g., `sudo apt install texlive-full`) or `texlive-latex-extra latexmk`
- macOS: MacTeX (or BasicTeX) — `latexmk` is included; if needed: `brew install latexmk`
- Windows: MiKTeX (enable on-the-fly package installation)

Verify tools:
```bash
latexmk -v
pdflatex --version
```

## Build

Run from the repository root.

- Build all PDFs:
```bash
latexmk
```

- Build a specific document:
```bash
latexmk src/productivity-cheatsheet-mac.tex
latexmk src/vim_cheat_sheet.tex
```

- Clean artifacts (keep PDFs):
```bash
latexmk -c
```

- Full clean (remove PDFs):
```bash
latexmk -C
```

PDFs are written to `build/` (configured in `latexmkrc`).
