# human-writing

## What this is

A method for writing or editing text so it is only as long as it needs to be and reads as written by a person. It combines three skills:

- **concise-writing** by Volker Otto ([l4ci/skills](https://github.com/l4ci/skills/tree/main/plugins/stray/skills/concise-writing)): the procedure, the cut ladder (delete whole units before trimming words), the question set, and the guardrail against over-trimming. It draws on [ponytail](https://github.com/DietrichGebert/ponytail) ("the best sentence is the one you never wrote"), Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), and Strunk and White, Zinsser, and Williams.
- **stop-slop** by Hardik Pandya ([hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)): the detailed catalog of slop phrases and structures (false agency, narrator distance, binary contrasts, business jargon, rhythm checks) and the five-dimension score.
- **humanizer** by Siqi Chen ([blader/humanizer](https://github.com/blader/humanizer)): the document-level patterns (text describing itself, replies that re-explain what the reader knows, heading echoes), borrowed authority, knowledge-limit guesses, tell strength (*weak alone*), the rule against inventing facts, and the file and embedded output modes.

## What it does

A single editor runs a loop: anchor to purpose and reader, draft or read, cut pass, de-slop pass, read-aloud and score, restore, final scan. The deliverable is the tightened text plus a word count, a score, and a short note on what did the most work. Named files are edited in place with code and paths left untouched; when another task embeds the skill (a commit message, a PR description), only the final text comes back.

Where the sources disagree, meaning wins: slop rules (no adverbs, no passive, no hedges) are strong defaults, but a qualifier that keeps a claim true stays. A rewrite never adds a fact the source does not have. Ask for the strict version if you want the rules applied as bans.

## When to use it

"tighten this", "make it shorter", "cut the fluff", "stop slop", "this reads like AI", "make it sound human", "write a concise X". Emails, posts, docs, announcements, READMEs, marketing copy, essays.

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
