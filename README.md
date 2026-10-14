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

## Workflow
1. Draft/approve bullet changes against source material (e.g. a work log).
2. Edit `Resume (Robotics+Ai).tex`; move any replaced bullets into `BULLET_LIBRARY.md` instead of deleting them.
3. Re-render the PDF and confirm it's still one page.
4. Log the change (what/why) in `CHANGELOG.md`.
5. Commit and push.
