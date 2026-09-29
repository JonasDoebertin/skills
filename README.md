# Jonas' Claude Code Skills

Personal Claude Code plugin with my own skills. The repository is both the plugin and a single-plugin marketplace.

## Installation

```text
/plugin marketplace add JonasDoebertin/skills
/plugin install dieserjonas@dieserjonas
```

Skills are then available namespaced as `/dieserjonas:<skill-name>`.

Update after new commits:

```text
/plugin marketplace update dieserjonas
```

## Local development

Load the plugin straight from the working copy without installing it:

```bash
claude --plugin-dir ~/Code/skills
```

Validate manifests and skills:

```bash
claude plugin validate .
```

## Structure

```text
.
├── .claude-plugin/
│   ├── plugin.json        # Plugin manifest
│   └── marketplace.json   # Marketplace listing (points to ./)
├── skills/                # One directory per skill, each with a SKILL.md
└── _template/             # Copy-paste template for new skills (not loaded)
```

## Adding a skill

1. `cp -r _template/skills/example-skill skills/<skill-name>`
2. Set `name` (must match the directory name) and a precise `description` in `SKILL.md`
3. Optional supporting files (`references/`, `scripts/`, `assets/`) go next to `SKILL.md`
4. Bump `version` in `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`

Skills adopted from third parties keep their original `LICENSE` inside the skill directory and note their origin in the skill's `README.md`.
