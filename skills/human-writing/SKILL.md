---
name: human-writing
description: Use when the user wants to write or edit text so it is only as long as it needs to be and reads as written by a person, with no AI slop. Anchors to the purpose and reader, runs the text down a cut ladder (delete whole units before trimming words), removes AI tells (filler phrases, formulaic structures, false agency, mechanical rhythm, em dashes), scores the result and loops draft to audit to final. Guards against over-trimming so the floor stays meaning, not word count. Triggers include "tighten this", "make it shorter", "cut the fluff", "less verbose", "trim this", "de-slop", "stop slop", "remove AI patterns", "AI tells", "this sounds AI-written", "make it sound human", "write a concise", "edit for length".
---

# human-writing

Writes new text, or edits existing text, so it is only as long as it needs to be and reads as human-written. Catches two failures at once: prose that is longer than its job requires, and prose that carries the tells of machine generation. The first is fixed by cutting whole units before trimming words; the second by rewriting the tells, not just striking them. The guardrail against both is the reader: a cut that costs meaning is a bad cut.

Load both reference files before working and follow them:

- [references/framework.md](references/framework.md): the premise, the cut ladder, the question set, the brevity moves, the length test, and the over-trimming guardrail ("what not to cut").
- [references/ai-tells.md](references/ai-tells.md): the catalog of AI tells (phrases, structures, rhythm, formatting) with the fix for each.

Worked material lives in [references/before-after.md](references/before-after.md) (short transformations) and [references/run-product-update-2026-06-24.md](references/run-product-update-2026-06-24.md) (a full run).

## Precedence

The two failure modes pull against each other: slop rules push toward deletion, the guardrail pushes toward keeping meaning. When they conflict, meaning wins.

- The rules in the tell catalog are strong defaults, not bans. Cut an adverb, hedge, or qualifier unless removing it changes what the sentence claims. "Most teams struggle" does not become "Teams struggle".
- Prefer active voice and name the actor. Passive is fine when the actor is unknown or irrelevant.
- "You" over "people" and "put the reader in the room" apply to essays, posts, and persuasive text. Reference and technical text stays neutral.
- Wh- sentence starters and three-item lists are heuristics: rewrite when they are a crutch, keep them when they are the clearest form.
- Em dashes, curly quotes, chatbot artifacts, and servile phrasing are the exception: always remove.

If the user asks for the strict version ("no adverbs at all", "zero passive"), drop the precedence and apply the catalog as bans.

## When to use

The user wants text written tight from the start, or an existing draft made shorter and less machine-sounding: emails, posts, docs, announcements, READMEs, marketing copy, essays. Reach for it on "tighten this", "make it shorter", "cut the fluff", "this reads like AI", "stop slop", or "write a concise X".

If the problem is not length or voice but the *order* of an argument (the answer should come first, the logic should be a pyramid), structure it first (for example with [scqa-pyramid](https://github.com/l4ci/skills/tree/main/plugins/latticework/skills/scqa-pyramid)), then use this skill to tighten the result.

## Language

Work in the language the user is writing in. The reference files are English; keep the framework and the tell-words keyed to it, but apply the spirit to the target language (every language has its own filler, its own throat-clearing, its own machine cadence, its own jargon).

## Inputs

- **MODE** (inferred): *edit* if the user hands you text to tighten, *write* if they hand you a brief to draft from. Do not ask; read what they gave you.
- **TEXT** (edit mode): the draft to tighten.
- **BRIEF** (write mode): what the text needs to say.
- **PURPOSE and READER** (required): what the text is for and who reads it. This is the anchor. You cannot judge "long enough" without it, so if it is not clear from the request, ask one short question before starting. Everything else is optional.
- **LENGTH** (optional): a hard target (a tweet, 200 words, one screen). Treat it as a ceiling, not a quota to fill.
- **REGISTER** (optional): formal, casual, technical, the voice to hold. Decides how the register-dependent rules in Precedence apply.
- **SAMPLE** (optional): a piece of the user's own writing to match for voice. If given, mirror its sentence rhythm and word level instead of defaulting to a neutral voice.

## Procedure

A single editor runs the loop; no fan-out is needed. The one optional exception is the audit (step 5), where a fresh reader catches what the author's eye skips.

1. **Anchor.** State, in one line, the purpose, the reader, and the single thing the reader must take away. Keep it in view; every later cut is judged against it.
2. **Draft or read.**
   - *Write mode:* draft the shortest version that does the job. Do not pad to a length.
   - *Edit mode:* read the whole text once for meaning before cutting a single word.
3. **Cut pass.** Run the cut ladder over the text, top down: kill whole sections and sentences that the takeaway does not need, then the restatements, then what the context already carries, then the long words and the scaffolding. Whole-unit cuts first; word-trimming last.
4. **De-slop pass.** Scan against the tell catalog: phrases, structures, false agency, narrator distance, rhythm. For each hit, rewrite the sentence around the concrete claim underneath it. Do not just delete the trigger word and leave a stump.
5. **Read-aloud and audit.** Read it aloud in your head: fix anything that stumbles, runs out of breath, or ticks along in a metronome rhythm. Then score the draft (below) and ask: *what is still longer than it needs to be, and what still reads as AI?* Answer in a few honest bullets and fix them. For a substantial piece, dispatch a fresh reader to answer the same question cold, since the author's eye forgives its own draft.
6. **Restore.** Check that no cut turned a true, qualified claim into a false absolute, and that the specifics, the needed qualifiers, and any wanted voice survived. Put back anything that lost meaning. The floor is the reader, not the word count.
7. **Final scan.** No em or en dashes, no curly quotes, no emoji unless the user asked for them, no boldface spam or Title Case headings. Any hit means the draft is not done.

### Score

Rate the draft 1 to 10 on each dimension. Below 35 of 50, revise. The score is an audit aid: it never overrides step 6.

| Dimension | Question |
| --- | --- |
| Directness | Statements, or announcements of statements? |
| Rhythm | Varied, or metronomic? |
| Trust | Does it respect the reader's intelligence? |
| Authenticity | Does it sound like a person wrote it? |
| Density | Is anything still cuttable? |

## Output

The deliverable is the tightened text itself, not a report about it. Deliver the final version inline. With it, give:

- A one-line before/after word count when you cut existing text.
- The score, as one line (for example "Directness 9, Rhythm 8, Trust 9, Authenticity 8, Density 9: 43/50").
- A short "what I cut and why" note: the few moves that did the most work (whole sections dropped, tells rewritten), not a line-by-line diff.

For a long piece, or when the user asks to keep a record, also save the final text plus the change note to `human-writing-<subject-slug>-<YYYY-MM-DD>.md` (today's date) in the working directory.

## Principles

- **Length is earned.** Every sentence justifies staying. Stop when the point lands; do not fill to a target.
- **Cut, do not compress.** Delete one whole sentence before you shorten ten.
- **Read before you cut.** You cannot tighten what you have not understood.
- **Rewrite tells, do not strike them.** A deleted trigger word in a still-generated sentence fixes nothing.
- **Name the actor.** People do things; complaints, data, and markets do not.
- **Specifics survive, filler dies.** Names, numbers, and examples are the last thing to cut.
- **As long as it needs to be, not as short as possible.** Terseness that drops a real point is a worse failure than a few extra words.
- **No em dashes.** Use a period, comma, colon, or parentheses.
