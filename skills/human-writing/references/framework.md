# human-writing (framework)

The method for writing or editing text so it is only as long as it needs to be and carries no signs of AI writing. Two ideas hold it together. First, from the laziness ethos of [ponytail](https://github.com/DietrichGebert/ponytail): the best sentence is the one you never wrote, so the default move is to cut, not to polish. Second, from Wikipedia's [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing): machine prose has specific, nameable tells, and you remove them by rewriting, not by striking words. A model writes the choice that fits the widest range of readers; a person writes for one reader, so the fix for every tell is to get specific. The classic concision sources sit underneath both: Strunk and White ("omit needless words"), Zinsser's *On Writing Well*, and Williams's *Style*.

The aim is not the shortest possible text. It is text as long as it needs to be: every cut that costs meaning is a bad cut. Brevity is a means, clarity is the end.

## The premise

Length is earned, not assumed. A reader's attention is the budget, and most drafts overspend it. So you start from the position that any given sentence, clause, or word has to justify staying. Default to cutting; keep what survives the question "does the reader lose something real without this?"

## The cut ladder

Run this top-down on every unit of text, from section to sentence to word. Each rung is cheaper than the one below it, so take the highest rung that applies before you reach for a lower one. This is the ponytail decision ladder turned on prose.

1. **Does this need to exist?** If the point stands without the sentence, the section, the caveat, the example, delete it. Whole-unit cuts beat word-level trimming every time. This is the rung people skip.
2. **Has it already been said?** Cut the restatement. Intros that preview, paragraphs that recap, the closing sentence that summarizes the paragraph above it.
3. **Does the context already carry it?** If the reader can infer it from what surrounds it, drop it. Stating the obvious is the most common form of length.
4. **Can a shorter word do the same work?** "Use" over "utilize", "now" over "at this point in time", "because" over "due to the fact that".
5. **Can the sentence stand without its scaffolding?** Strip the connective throat-clearing ("it is important to note that", "what this means is"), the hedges, the signposts. Say the thing.
6. **Only then, keep it,** in the fewest words that survive a read-aloud.

## The questions

Short questions to run a text through. They are the working procedure: answer them honestly and the cuts make themselves.

**Before writing or cutting:**
- What is this text for, and who reads it? (You cannot judge "long enough" without the job and the reader.)
- What is the one thing the reader must take away?
- What does the reader already know, so you do not have to say it?

**On the draft:**
- What can I delete without losing the takeaway?
- Which sentences restate a neighbor?
- Which words are doing no work? (Adjectives the noun implies, adverbs the verb implies, qualifiers that change nothing.)
- Where am I announcing what I am about to do instead of doing it?
- If I cut the last sentence of each paragraph, does the reader miss anything? (AI and habit both add wrap-up sentences that only recap.)
- Could a smart, busy reader get the same thing from half the words?

**On voice:**
- Does it read cleanly aloud, or does a sentence run out of breath?
- Does it sound like a person wrote it, or like it was generated?
- Did any cut turn a true, qualified claim into a false absolute? (If so, put the qualifier back.)

## The AI tells

The catalog of AI tells lives in [ai-tells.md](ai-tells.md). Run it as the de-slop pass after the cut pass. When you see a tell, rewrite the sentence around the concrete claim it is hiding; do not just delete the trigger word.

## Brevity moves the tell-list misses

Removing AI patterns is not the same as cutting length. These target verbosity directly:

- **Throat-clearing.** Delete openers that warm up before the point ("It goes without saying that", "When it comes to X").
- **One idea per sentence.** Split run-ons, then cut the weakest of the resulting sentences.
- **Verb over nominalization.** "decide", not "make a decision"; "consider", not "give consideration to".
- **Phrase to word.** "a large number of" to "many"; "in the event that" to "if".
- **Active over passive** when it shortens and names the actor.
- **Drop the recap.** The sentence that restates the paragraph it ends almost always goes.
- **Specifics, not quantifiers.** A number beats "several"; a name beats "various stakeholders". Use the number and the name the source has; if it has none, ask or keep the quantifier.
- **Stop when the point lands.** Do not write to fill a length. End the moment the reader has it.

## The length test

After a pass, ask: could a smart, busy reader get the same thing from half the words? If yes, you are not done. If cutting further would drop a real point or a needed qualifier, you are done. The floor is meaning, not word count.

## What not to cut

Conciseness is not terseness, and shorter is not always clearer. Over-trimming has its own failure mode. Do not:

- **Cut the qualifier that carries meaning.** "usually", "in most cases", "roughly" are not filler when they keep a claim from being false. Removing them to save a word is a bad trade.
- **Strip the concrete detail.** Specifics, examples, names, and numbers are what make writing useful and human. They are the last thing to cut, not the first. LLMs round detail off; do not finish the job for them.
- **Compress into jargon.** A denser noun phrase that is slower to parse is not a win. Optimize reading time, not character count.
- **Flatten the voice** where the genre wants one. An essay, a personal post, or an argument needs a person in it. Plain and neutral is correct for reference and technical text, not for everything.
- **Sand off real personality.** Asides, mixed feelings, a defended opinion, varied sentence length: these read as human and are worth their words.

The target is always "as long as it needs to be", judged against the purpose and the reader, not "as short as it can be".

## Sources

- ponytail, for the decision-ladder ethos applied to making: <https://github.com/DietrichGebert/ponytail>
- stop-slop by Hardik Pandya, for the phrase and structure catalogs: <https://github.com/hardikpandya/stop-slop>
- humanizer by Siqi Chen, for the document-level patterns, tell strength, and the no-invention rule: <https://github.com/blader/humanizer>
- Wikipedia, *Signs of AI writing*, maintained by WikiProject AI Cleanup: <https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing>
- Strunk and White, *The Elements of Style*; William Zinsser, *On Writing Well*; Joseph Williams, *Style: Toward Clarity and Grace*.
