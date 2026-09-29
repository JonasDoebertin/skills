# CLAUDE.md

This repository is a Claude Code plugin (`dieserjonas`) that doubles as its own marketplace (`dieserjonas`).

## Conventions

- Every skill lives in `skills/<skill-name>/SKILL.md`; the frontmatter `name` must equal the directory name (kebab-case).
- The `description` is the trigger: state what the skill does and when to use it, including concrete trigger phrases.
- Keep `SKILL.md` focused; move long reference material into `references/` and executable helpers into `scripts/` inside the skill directory.
- New skills start from `_template/skills/example-skill`.
- Any change to shipped skills bumps the semver `version` in `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json` (kept in sync), with an entry in `CHANGELOG.md`.
- New skills get a row in the README skills table.
- Run `claude plugin validate .` before committing.
- All content in English.
- Skills adopted from third parties keep their original `LICENSE` in the skill directory and state their origin (repo + commit) in the skill's `README.md`.
