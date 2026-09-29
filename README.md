# dieserjonas skills

![Version](https://img.shields.io/badge/version-0.1.0-blue)
![Claude Code plugin](https://img.shields.io/badge/Claude_Code-plugin-D97757)
![License: MIT](https://img.shields.io/badge/license-MIT-green)

My personal collection of [Claude Code](https://docs.claude.com/en/docs/claude-code) skills, shipped as one plugin. The repository is both the plugin and its own marketplace, so installing it takes two commands.

## Quick start

```text
/plugin marketplace add JonasDoebertin/skills
/plugin install dieserjonas@dieserjonas
```

Skills load automatically when a request matches their description. To call one explicitly, use `/dieserjonas:<skill-name>`.

To pull in new skills later:

```text
/plugin marketplace update dieserjonas
```

## Skills

| Skill | What it does | Try it with |
| --- | --- | --- |
| [human-writing](skills/human-writing) | Writes or edits text so it is only as long as it needs to be and reads as written by a person. Cuts whole sentences before trimming words, removes AI tells, scores the result, and puts back any qualifier whose loss changed the meaning. | "Tighten this email, it goes to customers" |

## Development

Load the plugin from the working copy instead of the installed version:

```bash
claude --plugin-dir ~/Code/skills
```

Check manifests and skills before committing:

```bash
claude plugin validate .
```

### Adding a skill

1. Copy the template: `cp -r _template/skills/example-skill skills/<skill-name>`
2. In `SKILL.md`, set `name` to the directory name and write a `description` that says what the skill does and when to use it. The description decides when Claude loads the skill.
3. Put long reference material in `references/` and helper scripts in `scripts/` next to `SKILL.md`.
4. Add the skill to the table above and to [CHANGELOG.md](CHANGELOG.md).
5. Bump `version` in `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json`, and the badge above.

Skills adopted from other people keep their original license inside the skill directory and name their source (repository and commit) in the skill's `README.md`.

### Layout

```text
.
├── .claude-plugin/
│   ├── plugin.json        # plugin manifest
│   └── marketplace.json   # marketplace listing, points to ./
├── skills/                # one directory per skill, each with a SKILL.md
├── _template/             # starting point for new skills, not loaded
├── CHANGELOG.md
└── LICENSE
```

## Credits

`human-writing` combines [concise-writing](https://github.com/l4ci/skills/tree/main/plugins/stray/skills/concise-writing) by Volker Otto and [stop-slop](https://github.com/hardikpandya/stop-slop) by Hardik Pandya, both MIT.

## License

[MIT](LICENSE) © Jonas Döbertin. Skills adapted from other projects carry their own license notices in their directories.
