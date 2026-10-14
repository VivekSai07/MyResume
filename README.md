---
type: system-doc
created: 2026-08-06
updated: 2026-10-14
tags: [readme]
---

# MyResume

Canonical resume for Vivek Sai (Robotics / Physical AI), tracked in git so changes and their
rationale are visible to any agent (Copilot, Claude, Codex) working in this repo — not just
in a chat session.

## Files
- `Resume (Robotics+Ai).tex` — LaTeX source, edit this, then re-render the PDF. Tuned to exactly one page.
- `Resume (Robotics+Ai).pdf` — rendered output, regenerate after editing the `.tex`.
- `Master Resume.md` — index note pointing to this repo's files and the private vault's deeper profile history (`01_Profile/Resume History`).
- `BULLET_LIBRARY.md` — full pool of bullets per role (used + cut), so trimmed bullets aren't lost.
- `CHANGELOG.md` — dated log of content/structure changes and why they happened.
- `.github/skills/` — resume-writing skills (ATS optimization, bullet writing, quantification, formatting, etc.), auto-discovered by agents working in this repo.

## LaTeX Setup Guide

This resume compiles with any standard TeX Live / MiKTeX distribution. The instructions below let a human or an agent on a fresh machine install the toolchain and build the PDF.

### Prerequisites

A LaTeX distribution with `pdflatex` and `latexmk`, plus the packages listed in the `.tex` preamble (all are part of the standard TeX Live "full" or "medium" schemes).

### Install — by OS

**Ubuntu / Debian / WSL:**
```bash
sudo apt-get update
sudo apt-get install -y texlive-full latexmk
# texlive-full is ~4 GB; for a lighter install:
# sudo apt-get install -y texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended texlive-fonts-extra latexmk
```

**macOS (Homebrew):**
```bash
brew install --cask mactex
# or for a smaller footprint:
# brew install --cask basictex && sudo tlmgr install latexmk collection-fontsrecommended collection-fontsextra enumitem titlesec marvosym babel hyperref tikz palatino
```

**Windows (native, not WSL):**
1. Download and install [MiKTeX](https://miktex.org/download) (select "Install missing packages on-the-fly: Yes").
2. Or install [TeX Live for Windows](https://tug.org/texlive/windows.html) with the full scheme.
3. Ensure `pdflatex` and `latexmk` are on your `PATH`.

**Docker (CI or any OS):**
```bash
docker run --rm -v "$(pwd):/work" -w /work texlive/texlive:latest \
  latexmk -pdf -interaction=nonstopmode "Resume (Robotics+Ai).tex"
```

### Build the PDF

```bash
# Recommended — handles cross-references and hyperlinks automatically
latexmk -pdf -interaction=nonstopmode "Resume (Robotics+Ai).tex"

# Single-pass alternative (faster, sufficient for most edits)
pdflatex -interaction=nonstopmode "Resume (Robotics+Ai).tex"
```

### Clean Build Artifacts

```bash
latexmk -c
```

### Verify

After building, confirm the PDF is **exactly one page** — this is a hard constraint. On Linux/macOS:
```bash
pdfinfo "Resume (Robotics+Ai).pdf" | grep Pages
# Expected output: Pages:          1
```

On Windows (PowerShell, if `pdfinfo` is not available):
```powershell
# Quick visual check — open the PDF
Start-Process "Resume (Robotics+Ai).pdf"
```

### Required LaTeX Packages

All of these ship with TeX Live full / MiKTeX auto-install. Listed here so a minimal install knows what to add:

`latexsym`, `fullpage`, `titlesec`, `marvosym`, `color` (dvipsnames), `verbatim`, `enumitem`, `hyperref`, `babel` (english), `tabularx`, `tikz`, `glyphtounicode`, `palatino`

## Workflow
1. Draft/approve bullet changes against source material (e.g. a work log).
2. Edit `Resume (Robotics+Ai).tex`; move any replaced bullets into `BULLET_LIBRARY.md` instead of deleting them.
3. Re-render the PDF and confirm it's still one page.
4. Log the change (what/why) in `CHANGELOG.md`.
5. Commit and push.
