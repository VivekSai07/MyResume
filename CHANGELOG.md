# Changelog

Notable content/structure changes to this resume repo, newest first.
Pairs with git history — see `git log --follow -- "Resume (Robotics+Ai).tex"` for raw diffs.

## 2026-10-14

### Changed
- Replaced all 4 Porsche Engineering Services bullets in `Resume (Robotics+Ai).tex` (generic, written
  before most of the 6-month internship's work had landed) with metrics-grounded bullets covering:
  perception/SLAM (cuVSLAM + nvblox, 30 Hz), object detection (YOLOv8/TensorRT, ~24 Hz),
  a SOLID-refactored detection-to-pose service (unit-tested), and the audio stack redesign (shared TTS
  scheduler + Nemotron ASR).
  - Source: `../WorkUpdates.md` entries from 22.04.2026 through 07.10.2026.
  - Skills applied: `tech-resume-optimizer`, `resume-bullet-writer`, `resume-quantifier`,
    `resume-ats-optimizer`, `resume-formatter` (see `.github/skills/`).
  - Replaced bullets and the broader cut-bullet pool preserved in `BULLET_LIBRARY.md` instead of
    being discarded.

### Added
- Installed 22 skills from [Paramchoudhary/ResumeSkills](https://github.com/Paramchoudhary/ResumeSkills)
  under `.github/skills/` for repo-scoped agent discovery (Copilot/Claude/Codex all read this path).
- Added `BULLET_LIBRARY.md` as the full bullet pool for this repo's resume (used + cut), since
  `Master Resume.md` intentionally delegates full profile history to the private vault.
- Added this `CHANGELOG.md`.

### Fixed
- `README.md` contained stale placeholder content ("Not yet populated...") referencing
  `00_System/AI/AI_RULES.md`, a path that only exists in the private vault, not this repo. Replaced
  with an accurate description of this repo's actual files.
