# human-writing

A Claude Code skill that cuts text to the length its reader needs and removes AI writing patterns (AI slop): filler, formulaic contrasts, false agency, mechanical rhythm, em dashes. It keeps the qualifiers that make a claim true and never adds facts the source lacks.

## Install

The skill ships with the `dieserjonas` plugin:

```text
/plugin marketplace add JonasDoebertin/skills
/plugin install dieserjonas@dieserjonas
```

To call it directly, use `/dieserjonas:human-writing`.

## Example

Before:

> Here's the thing: building products is hard. Not because the technology is complex. Because people are complex. Let that sink in.

After:

> Building products is hard because people are harder to handle than the technology.

The skill removed the opener, the "not because X, because Y" reversal, and the emphasis crutch. [references/before-after.md](references/before-after.md) has more pairs, and [references/run-product-update-2026-06-24.md](references/run-product-update-2026-06-24.md) shows a full run.

## What it does

It runs seven steps: anchor to purpose and reader, draft or read, cut pass, de-slop pass, read-aloud and score, restore, final scan. You get the tightened text plus a word count, a score, and a short note on what did the most work. Named files are edited in place with code and paths left untouched; when another task embeds the skill (a commit message, a PR description), only the final text comes back.

## When to use it

"tighten this", "make it shorter", "cut the fluff", "stop slop", "this reads like AI", "make it sound human", "write a concise X". Emails, posts, docs, announcements, READMEs, marketing copy, essays.

## How it differs from humanizer and stop-slop

It merges both with a third skill, concise-writing, and settles conflicts between their rules in favor of meaning. From each it takes a different part:

- **concise-writing** by Volker Otto ([l4ci/skills](https://github.com/l4ci/skills/tree/main/plugins/stray/skills/concise-writing)): the procedure, the cut ladder (delete whole units before trimming words), the question set, and the guardrail against over-trimming. It draws on [ponytail](https://github.com/DietrichGebert/ponytail) ("the best sentence is the one you never wrote"), Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), and Strunk and White, Zinsser, and Williams.
- **stop-slop** by Hardik Pandya ([hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)): the detailed catalog of slop phrases and structures (false agency, narrator distance, binary contrasts, business jargon, rhythm checks) and the five-dimension score.
- **humanizer** by Siqi Chen ([blader/humanizer](https://github.com/blader/humanizer)): the document-level patterns (text describing itself, replies that re-explain what the reader knows, heading echoes), borrowed authority, knowledge-limit guesses, tell strength (*weak alone*), the rule against inventing facts, and the file and embedded output modes.

## Will it cut too much?

When a slop rule and meaning conflict, meaning wins. The rules against adverbs, passive, and hedges are strong defaults, and a qualifier that keeps a claim true stays, so "Most teams struggle" does not become "Teams struggle". Ask for the strict version if you want the rules applied as bans.

## Does it work in other languages?

Yes. It writes and edits in the language you use. The tell catalog is in English, so in other languages the skill looks for the local versions of the same patterns.

## Files

- [SKILL.md](SKILL.md): procedure, precedence rule, score, output
- [references/framework.md](references/framework.md): cut ladder, questions, brevity moves, what not to cut
- [references/ai-tells.md](references/ai-tells.md): merged catalog of AI tells
- [references/before-after.md](references/before-after.md): short transformations
- [references/example.md](references/example.md) and [references/run-product-update-2026-06-24.md](references/run-product-update-2026-06-24.md): invocation and a full run

## Origin

Combined and adapted from:

- [l4ci/skills](https://github.com/l4ci/skills), `plugins/stray/skills/concise-writing`, commit `dbfdca4`, MIT, Copyright (c) 2026 Volker Otto
- [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop), commit `8da1f03`, MIT, Copyright (c) 2025 Hardik Pandya
- [blader/humanizer](https://github.com/blader/humanizer), v3.1.0, commit `225a6f3`, MIT, Copyright (c) 2025 Siqi Chen

All three license notices are in [LICENSE](LICENSE).
