# Changelog

All notable changes to this plugin are listed here. Versions follow [Semantic Versioning](https://semver.org).

## [0.2.1] - 2026-10-01

### Added

- README template for new skills in `_template/`.

### Changed

- Plugin and marketplace descriptions and keywords name what the skills do.
- `human-writing`: the README is now the skill's landing page, with install commands, an example, and answers to common questions.

## [0.2.0] - 2026-10-01

### Added

- `human-writing`: tells adopted from humanizer (blader/humanizer): text describing itself, replies that re-explain what the reader knows, heading echoes, arguing with no one, borrowed authority, vague association, knowledge-limit guesses, stock sections and send-offs, stock AI vocabulary, repeated openings, closers that explain the example.
- `human-writing`: file and embedded output modes.

### Changed

- `human-writing`: a rewrite never adds facts the source lacks; the restore step now checks for additions as well as losses.
- `human-writing`: tells are graded by strength, with *weak alone* tells acted on only in clusters.
- `human-writing`: the audit re-checks the tells that most often survive a rewrite.

## [0.1.0] - 2026-09-29

### Added

- Plugin and single-plugin marketplace `dieserjonas`.
- `human-writing` skill: concise, human-sounding prose. Combines concise-writing (l4ci/skills) and stop-slop (hardikpandya/stop-slop).
- Template for new skills in `_template/`.
