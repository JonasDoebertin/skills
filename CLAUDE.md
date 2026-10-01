# CLAUDE.md

This repository is a Claude Code plugin (`dieserjonas`) that doubles as its own marketplace (`dieserjonas`).

## Conventions

- Every skill lives in `skills/<skill-name>/SKILL.md`; the frontmatter `name` must equal the directory name (kebab-case).
- The `description` is the trigger: state what the skill does and when to use it, including concrete trigger phrases.
- Keep `SKILL.md` focused; move long reference material into `references/` and executable helpers into `scripts/` inside the skill directory.
- New skills start from `_template/skills/example-skill`.
- Any change to shipped skills bumps the semver `version` in `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json` (kept in sync), with an entry in `CHANGELOG.md`.
- Every skill has a `README.md` built from the template. GitHub shows it as the skill's own page, so it opens with the problem the skill solves in the words people search for, then install commands, an example, and answers to the questions people ask about it.
- New skills get a row in the README skills table, described the same way.
- Adding or removing a skill also updates the `description` and `keywords` in `.claude-plugin/plugin.json`, the plugin `description` in `.claude-plugin/marketplace.json`, and the repository description and topics on GitHub (`gh repo edit`).
- Run `claude plugin validate .` before committing.
- All content in English.
- Skills adopted from third parties keep their original `LICENSE` in the skill directory and state their origin (repo + commit) in the skill's `README.md`.
