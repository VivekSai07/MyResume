# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

Single-source-of-truth resume for **Vivek Sai** (Robotics / Physical AI). One LaTeX file, one PDF output, kept to exactly one page. This repo lives inside a larger CareerOS Obsidian vault — see `../CLAUDE.md` for vault-wide rules (especially `00_System/AI/AI_RULES.md` on what may and may not be invented).

## Build

Compile the resume and generate the PDF:

```bash
# Full build (recommended — handles references and hyperlinks)
latexmk -pdf -interaction=nonstopmode "Resume (Robotics+Ai).tex"

# Single-pass alternative
pdflatex -interaction=nonstopmode "Resume (Robotics+Ai).tex"
```

Clean build artifacts (`.aux`, `.log`, `.out`, `.synctex.gz`, etc.):

```bash
latexmk -c
```

After any `.tex` edit, always rebuild the PDF and verify it is still **exactly one page** before committing.

## Key Files

| File | Role |
|------|------|
| `Resume (Robotics+Ai).tex` | LaTeX source — the only file to edit for resume content |
| `Resume (Robotics+Ai).pdf` | Rendered output — regenerate after every `.tex` change |
| `BULLET_LIBRARY.md` | Pool of all bullets per role (used + cut); never delete a bullet, move it here |
| `CHANGELOG.md` | Dated log of content/structure changes and rationale |
| `Master Resume.md` | Obsidian index note linking this repo to the private vault's profile history |
| `.github/skills/` | 22 resume-writing skills auto-discovered by agents (ATS, bullet writing, quantification, etc.) |

## Editing Rules

- **Never invent resume content.** All bullets must trace to source material (e.g. `../WorkUpdates.md`). If no source exists, ask — do not fabricate.
- **One-page constraint is hard.** If adding a bullet, remove or shorten another. The PDF must not spill to page 2.
- **Replaced bullets go to `BULLET_LIBRARY.md`**, not deleted. Tag them with the date and ATS keywords they cover.
- **Log every change** in `CHANGELOG.md` (what changed, why, which skills were applied).
- **Commit workflow:** edit `.tex` → rebuild PDF → verify one page → update `BULLET_LIBRARY.md` if bullets changed → update `CHANGELOG.md` → commit both source and PDF.

## LaTeX Structure

The `.tex` uses custom commands defined in its preamble — use them consistently:

- `\CVSubheading{title}{dates}{org}{location}` — work experience header
- `\CVItem{text}` — individual bullet point
- `\CVProject{title}{date}` — project header
- `\CVEduItem{school}{dates}{degree}{location}` — education entry
- `\CVItemListStart` / `\CVItemListEnd` — wraps bullet lists
- `\CVSubHeadingListStart` / `\CVSubHeadingListEnd` — wraps section entries

Paper size is A4 with tight margins. The `palatino` font and `hyperref` (NavyBlue links) are used. Date text uses `\textcolor{datecolor}{...}` (hex `#2E6DA4`).

## Repo Context

This is a subfolder (`09_Resumes/Master`) of a CareerOS Obsidian vault. Notes use YAML frontmatter (`type`, `created`, `updated`, `tags`). The vault's AI rules in `00_System/AI/` govern what agents may do — read them before creating or editing any `.md` file outside this repo.
