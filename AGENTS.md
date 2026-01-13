# AGENTS.md

## Build & Compile Commands

**Build all PDFs:**
```bash
latexmk
```

**Build specific document:**
```bash
latexmk src/productivity-cheatsheet-mac.tex
latexmk src/vim_cheat_sheet.tex
latexmk src/claude_code_cheatsheet.tex
```

**Clean build artifacts:**
```bash
latexmk -c
```

**Full clean (remove PDFs):**
```bash
latexmk -C
```

PDFs are output to `build/` directory. Configuration in `latexmkrc`.

## Code Style & Conventions

- **Structure**: Each `.tex` file is self-contained; variant wrappers (`-mac.tex`, `-windows.tex`) use `\def\MACONLY{}` or `\def\WINONLY{}` then `\input{src/productivity-cheatsheet.tex}`
- **Conditional includes**: Use `\ifdefined\MACONLY` / `\ifdefined\WINONLY` to branch content
- **Imports**: Standard LaTeX packages only (multicol, xcolor, geometry, tcolorbox, etc.)
- **Naming**: CamelCase for commands; use descriptive names like `\sectioncolor`, `\windowscolor`
- **Formatting**: 2-space indentation, compact spacing (lists use `noitemsep`), landscape orientation for cheat sheets
- **Colors**: Define at document start with `\definecolor{}` and reuse with semantic names
- **Margins**: Typically 0.5in-1cm; geometry package handles sizing
- **No external dependencies**: Self-contained `.tex` files; no need for build tools beyond `latexmk`

## Tips

- Modify `latexmkrc` to change default build behavior
- Use `\iffalse...\fi` or conditionals for debugging or OS-specific content
- PDFs preserve in `build/` after cleanup unless `-C` flag used
