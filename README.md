# Claude Code skills by Jonas Döbertin

![Claude Code plugin](https://img.shields.io/badge/Claude_Code-plugin-D97757)
![License: MIT](https://img.shields.io/badge/license-MIT-green)

My personal [Claude Code](https://docs.claude.com/en/docs/claude-code) skills, packaged as one plugin called `dieserjonas`. The repository is also its own plugin marketplace, so two commands install every skill.

## Install

```text
/plugin marketplace add JonasDoebertin/skills
/plugin install dieserjonas@dieserjonas
```

Claude loads a skill when your request matches its description. To call one directly, use `/dieserjonas:<skill-name>`. Run `/plugin marketplace update dieserjonas` to get new skills.

## Skills

| Skill | What it does | Try |
| --- | --- | --- |
| [human-writing](skills/human-writing) | Cuts text to the length its reader needs and removes AI writing patterns (AI slop), without dropping qualifiers that carry meaning. For emails, docs, READMEs, and posts. | "Tighten this email to our customers" |

## Development

Run Claude against the working copy instead of the installed plugin, and validate before you commit:

```bash
claude --plugin-dir ~/Code/skills
claude plugin validate .
```

To add a skill:

1. `cp -r _template/skills/example-skill skills/<skill-name>`
2. In `SKILL.md`, set `name` to the directory name. Write the `description` carefully: it decides when Claude loads the skill.
3. Put long reference material in `references/` and scripts in `scripts/`, next to `SKILL.md`.
4. Fill in `README.md`. GitHub shows it as the skill's own page, so its first sentence should name the problem the skill solves in the words people search for.
5. Add a row to the table above and an entry to [CHANGELOG.md](CHANGELOG.md).
6. Bump `version` in `.claude-plugin/plugin.json` and `.claude-plugin/marketplace.json`, and add the skill's search terms to `keywords`.
7. Update the repository description and topics on GitHub.

A skill adopted from someone else keeps its original `LICENSE` in its directory, and its `README.md` names the source repository and commit.

```text
.claude-plugin/   plugin.json and marketplace.json
skills/           one directory per skill, each with a SKILL.md
_template/        starting point for new skills, not loaded
```

## Credits and license

`human-writing` combines [concise-writing](https://github.com/l4ci/skills/tree/main/plugins/stray/skills/concise-writing) by Volker Otto, [stop-slop](https://github.com/hardikpandya/stop-slop) by Hardik Pandya, and [humanizer](https://github.com/blader/humanizer) by Siqi Chen, all MIT.

Everything else is [MIT](LICENSE) © Jonas Döbertin.
