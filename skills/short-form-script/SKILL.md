---
name: short-form-script
description: "Write the Italian script for a vertical short-form video (Reels, TikTok, Shorts), from any folder: a tool, a set of tools, a concept, a news item, a story, a tutorial, an opinion. First it writes one hook per type (shock, completo, errore, confronto, domanda, negativo, tutorial, notizia), ranks them with the content-principles psychology and lets the user pick. The pick decides the skeleton: the default (hook, super hook, open loop, body + rehook × N, payoff and CTA), the set (hook, the set, one item per tool, CTA) or *problema → sistema* for tutorials. Then it humanizes the script with the `umanizzatore` skill. Use when the user wants a script or copione, a hook or hook ideas, a reel, a Short or a TikTok, a \"5 plugin\" style list, or asks to turn research, a reference clip or an idea into a script."
---

# Short-form script

Writes the **words**, in Italian, timed to the beat, for every short-form video the user makes, whatever it is about. Not the cut: that is `video-making-cut`. Not the research: that is `video-making-reference`. Both live in `~/Projects/video-making`, where every video folder, `INDEX.csv` and the script files live too.

This skill works from any folder. It ships in the `content-creation` plugin, whose repo is `~/Projects/content-creation`; this skill is `skills/short-form-script/` there. Edit it in the repo, never in the installed copy under `~/.claude/plugins/`. Then bump `version` in `.claude-plugin/plugin.json` and run `claude plugin update content-creation@content-creation`; it applies after a restart.

The order is fixed: two questions, **the hook step**, the skeleton, the script, `umanizzatore`, the deliverable. Three skeletons: the default, the *set* for videos that name tools, and *problema → sistema* for tutorials. Within a skeleton, a tool, a concept and a story differ in what fills the beats, never in the beats.

## Read first

- [references/content-principles.md](references/content-principles.md): the psychology of attention in short form (aiwithremy's skill, verbatim). Read it before every script and let it shape every line. Where it conflicts with this skill, this skill wins: see *Where the house rules win*.
- [references/hooks.md](references/hooks.md): the hook catalogue, for the hook step.
- [references/voice.md](references/voice.md): the user's own scripts, for register.
- `~/Projects/video-making/reference/PATTERNS.md`: Saraev's 18 reels, for timing evidence. Its list rules and its separate YouTube ending are superseded here.

## The viewer

content-principles §1 asks who the one viewer is. The answer, so you do not ask every time: **one Italian who uses AI tools and agents** (ChatGPT, Claude, Claude Code, Codex) and wants to get more out of them. Some write code, most do not, so every line passes the 10-year-old test and commands go on screen, never in the voice. Speak to that one person, `tu`. Swap US-only tips for Italian equivalents or drop them.

## Before writing: two questions

1. **What is actually verified?** Get the claims straight before the phrasing. Star counts, free tiers, provider counts and "official" attributions are the load-bearing parts and the ones that rot fastest. Anything you cannot confirm does not go in the script: write the beat without a number rather than with a soft one.
2. **What is the payoff?** Name, in one sentence, the last thing the viewer gets. Every hook candidate promises it, so it has to exist before they do. If you cannot name it, the video is not ready to script.

Never invent a statistic, a star count, a price or a capability. If the user supplies one, attribute it in the notes so they know it is theirs, not yours.

**Only the positive side.** The spoken lines never mention a downside of the subject: no limits, no caveats, no "what nobody tells you", no terms-of-service warnings, no "don't connect X". They carry the benefits and the opportunities. Leave the negative out; never deny it or claim the opposite. Every line stays true and specific enough not to mislead: name the models Claude Code runs on, so nobody hears "Claude gratis". The research sections (*Claim da verificare*, *Note*) still record limits and conflicting sources, because they are for the user, not the viewer. A problem the subject solves is not a downside: the viewer's situation today ("gli agenti AI non possono guardare i video") is the *problema* beat of the tutorial skeleton, and the viewer's habit is what an `errore` or `negativo` hook points at. What stays out is any flaw of the subject itself. The user set this rule on 2026-09-28, after a FreeLLMAPI draft used a daily-limit rehook and a terms-of-service warning as its payoff.

**Keep the reference's promise, and sell the advantage.** When the script starts from a reference clip, its value proposition is why the user picked it: keep it as the promise and the payoff, and change the words, not the promise. Every line says what the viewer, or the viewer's agent, can now do. What the tool does gets one short clause, in the beat that introduces it ("Claude Watch, che permette all'agente di scaricare, estrarre fotogrammi e trascrivere video"); a body is never spent on how it works inside. **Cut every benefit that does not serve the main promise**, even a true one, even "gratis": the user dropped Watch's free Gemini engine because teaching the agent did not need it. The user set this rule on 2026-10-01, after a Watch draft swapped the reference's "teach your agent anything from YouTube" for "skip watching tutorials" and spent its bodies on frames and transcripts.

### Voice: `references/voice.md`

Every comparison with past scripts (voice sample, audit 6) uses [references/voice.md](references/voice.md): the user's own scripts, verbatim, chosen by the user, with the phrases that are voice listed at the top. Nothing else counts as the user's voice. Not a local `script.md` (Claude's draft), not the transcript of a recorded take, not a Notion page because its status says Published: on 2026-10-01 the newest Published pages included one Claude adaptation, and the user called reading them a mistake.

Use it lightly. It shows the register and what to avoid repeating; it is not a template, and when it differs from this skill, the skill wins. Its hooks, loops and claims are what you do not copy. Leaning on past scripts anchors every new one to the old quality and slows improvement (the user, 2026-09-29).

## Step 1: pick the hook

The same idea becomes a different video depending on its hook, so the hook is chosen before anything else is written. This step replaces "decide which feeling first" (the user, 2026-10-26).

1. **Write one candidate per type** in [references/hooks.md](references/hooks.md), all on the same idea and all promising the payoff. The shapes there are examples: write the one that fits this idea. Drop a type that cannot be honest for this subject, with the reason in one line ("`notizia`: uscito a giugno, *appena* sarebbe falso").
2. **Rank them** with content-principles: the size of the gap against the time asked (§2, §7); a specific object, a number, a name or a date, rather than a category (§5); the 10-year-old test, and the idea in ten words or fewer (§6); whether the line makes the next one necessary (§3). Recommend one, with the reason in a line.
3. **Show the user a table**: type · hook · what the video becomes (from `hooks.md`). Then stop and wait. The user may pick one, mix two, or rewrite one.
4. **Record it.** The pick is the `hook_type` in `INDEX.csv`; the other candidates go into `script.md` under *Hook candidati*.

Every candidate keeps these rules:

- No greeting, no name, no "in questo video".
- **Lead with what the viewer gains, in everyday terms**: money, time, effort. Not the mechanism, not a list of brand names. The user rewrote "Così usi i piani gratis di Gemini, Mistral, Groq e NVIDIA con una chiave sola" as "Forse non sai che puoi smettere di pagare per le chiavi API per i tuoi progetti di intelligenza artificiale" (FreeLLMAPI, 2026-09-29). The one key moved into the body.
- If a feeling word appears, say it plainly ("mi ha fatto arrabbiare"), never through the body ("mi si è gelato il sangue"): structural audit 3.
- Outcome first works well: the hook line runs over the proof on screen.

## Step 2: pick the skeleton

- **A draft that names its tools is a set**, whatever the title says ("Come usare…" included): a few sentences per tool on what it does and how you use it, even with only two tools. Never turn it into steps of a method. The user set this on 2026-10-14, after a two-tool cyber-security draft came back as a three-step tutorial.
- Otherwise the hook decides: `tutorial` takes *problema → sistema*, `completo` takes the set, every other type takes the default.

Total length **30s to 2 min**, set by the content: the video runs as long as its beats carry real value, and no longer. There is no fixed target in between (the user, 2026-09-29).

## The default skeleton

**hook → super hook → open loop → (body → rehook) × N → payoff + CTA.**

| Beat | Time | Job |
|---|---|---|
| Hook | 0–3s | The pick from step 1. One sentence. |
| Super hook | 3–8s | Authority (why listen to this, from you, now) or a premise the viewer agrees with. It carries a fact. |
| Open loop | by 10s | Promise one specific thing that only the end delivers. |
| Body → rehook, × N | 10s to end−6s | Body gives real value. Rehook gives a new reason to stay. |
| Payoff + CTA | last 5–8s | Pay the loop, then the CTA. Nothing after it but the agent shortcut. |

Beats may share a sentence: super hook and open loop often fit in one ("43.000 stelle su GitHub, e il terzo comando è quello che non usa nessuno"). The order never changes.

The skeleton costs words: hook, super hook, loop and rehooks take 30–40 words at any length. Cut adjectives and empty connectives inside the bodies before you drop a beat.

### Super hook: authority or premise

Right after the hook, one reason to keep listening. Either a premise the viewer already agrees with, or authority that is named and checkable.

**A premise** is a question with an obvious answer that sets up what follows: "Se ti chiedessi: nel 2026, dove si trova la maggior parte della conoscenza vera disponibile online? Ovviamente su YouTube." (Claude Watch, the user, 2026-10-01). It proves nothing about the subject; it makes the problem feel inevitable. It must be something the viewer already believes, never a statistic in disguise. Record it under *Claim da verificare* as an opinion. It is the usual second beat of *problema → sistema*.

**Authority** is one of:

- a number with its date: GitHub stars, downloads, users;
- a named origin: Stanford, Google, a paper in *Nature*;
- first-hand use: "lo uso da tre mesi per…", "l'ho rifatto in italiano";
- the demo itself: when the proof is on screen, it is the authority (`bias-google`);
- what it is and at what scale, with its name: "FreeLLMAPI è un progetto open source che mette insieme i piani gratuiti di decine di provider". A star count is optional; the scale often carries the beat on its own.

Never borrowed authority: "gli esperti dicono", "tutti ne parlano", "sta spopolando". That is humanizer §17 and structural audit 4. With nothing checkable, first-hand use or the demo carries the beat.

### Open loop: commit them to the end

One specific promise that only the payoff pays. Specific means the viewer can tell whether it was paid: "alla fine ti dico quale dei tre uso io", "e perché l'ho disinstallato dopo una settimana te lo dico alla fine".

- **Exactly one** main loop per video. With a `domanda` hook, the question is the loop.
- **Never vague.** "Resta fino alla fine" and "il meglio arriva alla fine" promise nothing the viewer could check, so they are not a loop.
- **Never gate the answer.** The loop pays off on screen, inside the video. The comment-gate hands over a link or a file, never the thing the loop promised.
- In a step-by-step video, "ecco il sistema che ti serve per…" plus numbered steps open the loop, and the last step pays it. No separate "te lo faccio vedere alla fine".
- **The payoff is something the viewer gets**: a capability they can use, time or money they save, a way to have it free. Never a third party's result, a name held back or a number to reveal ("quante review ci ha scritto un neuroscienziato"): waiting for it gains the viewer nothing. Proof like that belongs in a body. The user set this rule on 2026-09-29, after a Claude Science draft did exactly that.
- **Natural, never forced.** The loop follows from what the hook and super hook just said, so it sounds like the next sentence of the script, not a teaser bolted on. If the link to the rest takes effort to explain, pick another payoff.
- Among those benefits, **promise the most surprising one**, best set against a named giant: "qualcosa di speciale che i provider a pagamento come OpenAI e Anthropic non sono in grado di fare". Never a setup step or a command: a procedure is not a reason to stay, although a way to get it free is.

### Body and rehook, × N

**Body: real value.** One idea per body, concrete enough that the viewer can picture the screen. A body answers something; it does not tease. No adjective doing a verb's job. Say what the viewer does and gets ("tu fai una domanda come al solito"), not how to configure it: commands, flags and model ids go on screen, never in the voice. The hook type shapes the bodies: see "The video" under each type in `hooks.md`.

**Rehook: a new reason to stay.** One sentence at the end of each body, before attention drops, every 7–12s. It opens a small loop that the next body closes: a stake, a twist, a new capability, a number that changes the picture. Never a limit (see *Only the positive side*). It must carry information of its own. Around 60–70% of the video, after the main promise is mostly paid, one rehook opens a fresh loop so the viewer never feels done early (content-principles §4).

- Lead with the benefit, then name the feature: "E se vuoi risposte ancora più robuste, puoi usare l'approccio fusion" beats "E se la stessa domanda la vuoi fare a più modelli insieme?".
- Good: "Infine, puoi usare questo router anche con gli agenti che scrivono codice." · "Il secondo è gratis, e fa quello che il primo non fa."
- Empty, cut on sight: "Ma non è finita." · "E non è tutto." · "Ma aspetta." They carry no information, so they fail the rule above.
- Vary the form inside one script: not three questions in a row.
- **N**: as many bodies as the content really has, 2–3 in a short video and more in a long one.
- The last rehook turns toward the payoff.

### Payoff + CTA: close the loop

Pay the open loop explicitly, close enough to its wording that the viewer recognises the promise being kept. A callback to the hook is strong here: an early detail that now means something new. The CTA comes straight after.

- **End hot.** No summary, no moral, no "questo è il punto" after the payoff. A wrap-up coda is structural audit 1, and it is the Claude fingerprint the structural pass warns about.
- The CTA can ride on the payoff ("il link al terzo te lo mando: commenta TERZO").
- **The CTA may offer a guide**: "Se commenti LUMINARE ti mando la guida e la repo." The guide must exist before the video is published; list it under *Note* as a task (the `website-resource` skill makes it).
- **One line may follow the CTA: the agent shortcut.** "E se preferisci che questo sistema lo costruisca il tuo agente al posto tuo, salva questo video e mandalo dritto a lui insieme alla guida." It asks for a save and a send, the strongest signals, after the comment. It works only when the agent can read what it is sent: the guide (and the post caption) must hold the repo and every step written out, because the agent cannot watch the reel before it has the tool. The user moved it there from the reference's 0:11 on 2026-10-01.

### One CTA for every platform

One master goes to Reels, TikTok and Shorts, so there is **one script with one CTA**: the Instagram comment-gate ("Commenta X e ti mando il link"). The video is cross-posted unchanged, and on TikTok and YouTube the user answers comments by hand. Write no alternative ending (the user, 2026-10-26). These rules hold in all three skeletons.

## The set skeleton

**hook → the set → item × N → CTA.** For any video that names its tools. It comes from the user's *ai-cybersecurity* script (published October 2026, https://app.notion.com/p/3e2f4b208c4080b0b4d1cdad03ad4c0c). About 45 s for two items.

| Beat | Job | ai-cybersecurity |
|---|---|---|
| Hook | The pick from step 1 | "Tutti sempre a dire che le app create con l'AI non sono sicure, ma da oggi le cose cambiano." |
| The set | How many, and the one benefit they share; it may carry the authority ("gratuiti") | "Esistono infatti due strumenti gratuiti che rivoltano il tuo codice come un calzino e permettono di sistemare eventuali problemi di cybersicurezza." |
| Item 1…N | Ordinal and name, one clause of authority or of what it is → how you use it, as the viewer's actions → what you get. A few sentences each | "Il primo è security-audit, la skill che anche Cloudflare usa sul proprio codice. La installi nel tuo agente e gli chiedi un audit e lui cerca le falle ovunque…" |
| CTA | Comment-gate; the guide and the links to every item | "Commenta BOTTE DI FERRO e ti mando una guida e il link a tutti e due." |

- **No open loop and no rehook line.** "Il secondo è…" is the rehook, as "Step N:" is in a tutorial: each ordinal promises the next one.
- **As many items as the content has.** No fixed count, no fixed order, no fixed shape across items (the user dropped the old 3–5 item rules on 2026-10-26).
- Each item is a tool the viewer could use on its own. One method in order is *problema → sistema*, never a set.
- With a `confronto` hook, the last item ends on the verdict.
- The agent shortcut may follow the CTA, as in the default skeleton.
- Beat names for *Struttura*: `hook`, `set`, `item N`, `CTA`.

## The tutorial skeleton: problema → sistema

**hook → premessa → problema → sistema → Step 1…N → CTA → scorciatoia agente.** For tutorials and any video that hands the viewer a method ("il sistema per…"). It comes from the user's Claude Watch script (2026-10-01, in [references/voice.md](references/voice.md)), adapted from the structure of Jens Heitmann's reel `~/Projects/video-making/reference/heitmann-Db1USzsMNnZ/`, which the user liked. About 50 s.

| Beat | Job | Claude Watch |
|---|---|---|
| Hook | The pick from step 1, usually `tutorial`; a short tease may follow | "E se ti dicessi che c'è un modo per trasformare il tuo agente AI in un super esperto in tutto? E l'approccio ti sorprenderà." |
| Premessa | A question the viewer can only agree with (see *Super hook*) | "…dove si trova la maggior parte della conoscenza vera disponibile online? Ovviamente su YouTube." |
| Problema | What stops the viewer today. Never a flaw of the subject | "Ma c'è un problema, perché gli agenti AI non possono guardare i video…" |
| Sistema | The creator as guide, first person; restates the promise and opens the loop | "Ma non preoccuparti, ci ho pensato io. Quindi ecco il sistema che ti serve per insegnare ai tuoi agenti praticamente qualsiasi cosa." |
| Step 1…N | **tool → use → scale**: install the tool (one clause on what it does), use it once, then repeat or combine. Each step one or two sentences. "Step N:" is the rehook | "Step 3: Ripeti il processo per ciascun video e tutorial o combina più video in una stessa skill e il tuo agente non avrà più limiti." |
| CTA | Comment-gate; may offer the guide and the repo | "Se commenti LUMINARE ti mando la guida e la repo." |
| Scorciatoia agente | Save and send the video to the agent, with the guide | see *Payoff + CTA* |

- The last step is the payoff: it escalates the hook's promise ("non avrà più limiti").
- Three steps unless the content really has more. The steps are one method in order, not a set.
- Beat names for *Struttura*: `hook`, `premessa`, `problema`, `sistema`, `step N`, `CTA`, `scorciatoia agente`.

## Filling the body, by content type

| Content type | `format` | Skeleton | The bodies carry | Super hook, usually |
|---|---|---|---|---|
| Single tool | `single` | default | 2–3 capabilities, one per body; the cost said plainly in the last one ("è gratis" when true) | what it is and at what scale; stars or downloads with the date; a named maker |
| Tool set | `set-N` | set | one item per tool | the set beat |
| Concept / explainer | `single` | default | the demo, the mechanism, why it concerns the viewer | the demo; a named study |
| News | `single` | default | what happened, what changes for the viewer, what it opens up | the named source and the date |
| Story / experience | `single` | default | events in order, with one turn; feelings named plainly | first-hand |
| Tutorial | `single` | problema → sistema | one step per body, tool → use → scale | a premise the viewer agrees with; or the outcome, shown in the hook |
| Opinion | `single` | default | the claim, the evidence, what the viewer gains by acting on it | first-hand, track record |

## Where the house rules win

`references/content-principles.md` applies everywhere, except where it meets these rules:

- **Formats.** Its stance says to throw out any structure you can name. The three skeletons and the hook catalogue are the user's choice (2026-09-29, 2026-10-26) and stay; the principles work inside the beats, on every line.
- **Sentence length (§8).** Keep full spoken sentences with their subjects (*Italian craft rules*). Take from §8 one idea per sentence, not a word count.
- **Objections (§9).** Disarm the viewer's doubt in a short aside ("senza scrivere codice", "è gratis"); never by naming a limit of the subject (*Only the positive side*).
- **The viewer (§1).** Answered under *The viewer*; do not ask every time.
- **Value by 5–10 s (§7).** The super hook carries a fact, not a mood; in a set the first item starts by about 8 s.
- **Specificity (§5)** never licenses an unverified number: a beat without a number beats one with a soft number.
- **The frame (§10)** belongs to the cut (`video-making-cut`). For the script it means distinct beats, which give the edit places to cut.

## Humanize with `umanizzatore`

Every script goes through the `umanizzatore` skill before delivery. Draft the whole script first. `umanizzatore` runs `humanizer` v3.1.0, then its Italian catalog, then `structural-humanizer`. Its catalog holds only tells that a cited source names in Italian, or house preferences with a date and a reason. Do not add Italian tells here: new ones go into that catalog, from a source or as a preference the user decides.

1. **Voice sample.** [references/voice.md](references/voice.md), for register: sentence length, tone and the phrases the user keeps writing. The sample overrides humanizer: "Funziona così:" looks like a §4 staged run-up, and "E se ti dicessi…" a staged question, and both stay.
2. **Embedded mode.** Return only the final text.
3. **Structural pass, calibrated for these skeletons.** Audit the beat list, not the prose. Even at 2 min a script is short text (~460 words), so the short-text rule applies: audits 1, 3, 4 and 6.
   - **Audit 1, theme**: state the point once. Nothing after the payoff but the CTA and the agent shortcut.
   - **Audit 2, tidiness**: does not apply to the main loop. Closing it is the contract with the viewer. A minor thread may stay open as the next video.
   - **Audit 3, emotion**: name feelings plainly, no body performance.
   - **Audit 4, named things**: every tool, company, number and date by name.
   - **Audit 5, reader**: `tu` already covers it. At most one line that admits the viewer is watching.
   - **Audit 6, shape convergence**: the skeletons are fixed on purpose, so judge convergence inside them. Against the scripts in `references/voice.md`, compare hook type, super hook kind, open-loop wording, rehook forms and CTA word. Change at least the hook type and the open-loop wording.
   - **Interventions**: pick one or two per script from the skill's menu and record them under *Struttura*. The ones that fit these skeletons: outcome first, delayed reveal, recontextualization callback, the named thing, plain emotion, end hot.
4. **Read it line by line** (content-principles §3): does each line make the next one necessary? A line that does not is cut or rewritten, however good it is.
5. **Scan the spoken lines.**

   ```bash
   sed -n '/^## Testo/,/^## /{/^## /d;p}' <video folder>/edit/script.md | python3 ~/.claude/skills/umanizzatore/scripts/scan_it.py -
   ```

   A clean scan means only that the mechanical tells are absent. The scanner prints each hit's strength: a "debole da solo" hit justifies an edit only alongside other tells in the same passage.

## Italian craft rules

- **`tu`, always.** One viewer, not an audience. No "ragazzi": it is the tic that marks translated-from-English content.
- **Italian runs 10–15% longer than English** at equal content. Cut empty connectives ("in pratica", "e quindi") before you cut substance.
- **Written for the ear.** Connectives that announce the next beat stay: "Funziona così:", "Infine", "Quindi" guide someone who is listening, not reading. Full sentences with their subjects ("tu scarichi l'app…, lui si sceglie il modello…"), not telegraphic fragments cut to hit a word count.
- **"Il tuo agente", by default.** The audience uses Claude Code, Codex and others. Say "il tuo agente AI" and name a product only where a step differs between them: "Claude Code lo fa con skill-creator, la skill ufficiale di Anthropic, mentre Codex ce l'ha già di serie" (the user, 2026-10-01).
- **Keep the technical terms in English**: plugin, token, hook, skill, prompt, MCP, codebase, tool, router. Translating them reads academic to this audience. *Agent* is the exception: the user writes "agenti".
- **Numbers in Italian convention**: decimal comma, `1,6 miliardi`, `€` after the figure.
- Read it aloud against a timer and write the estimated duration in *Note*. Time it at his measured pace, ~180 words/minute after the cut, not a generic 230: open-feed-sorter (2026-10-06) cut to 174 spoken words in 57 s, where its draft had promised ~41 s, and freellmapi's 188-word script ran 69 s. So 30s is ~90 words, 1 min ~180, 2 min ~360. The length follows the content: never squeeze lines into fragments to hit a number. Cut only what carries no value.

## Deliverable

Write to `~/Projects/video-making/<video folder>/edit/script.md`. The spoken text goes under *Testo* as plain paragraphs, one per beat, with no timestamps, beat labels or other markup, so the user can copy the whole block straight into a teleprompter or Notion (the user, 2026-10-26). The beat map lives under *Struttura*. In chat, show the script the same way: the plain text first, in one block, then the rest.

```markdown
# <title> · <single|set-N> · <default|set|problema → sistema> · ~<NN>s

## Testo

<hook>

<super hook>

<open loop>

<body 1>

<rehook>

…

<payoff>

<CTA>

## Hook candidati
- `<hook_type>` (scelto): <the hook used>
- `<hook_type>`: <candidate>
- `<hook_type>`: scartato, <why it could not be honest>
- …

## Struttura
- Beat: hook "<first words>" · super hook "<first words>" · open loop "<first words>" · … · CTA "<first words>"
- Hook: <hook_type>, scelto fra <N> candidati perché <the reason>
- Super hook: <the source of authority>
- Open loop: "<the promise>", pagato nel payoff
- Rehook: <the forms used>
- Interventi strutturali: <one or two from the menu, and why>
- Rispetto a voice.md: <what changed>

## Claim da verificare
- <every number and attribution in the script, with its source or "fornito dall'utente">

## Note
- <word count, estimated duration, anything cut for length, the guide to make>
```

## Then update the index

**When the user hands back a rewrite**, write it to Dori's content calendar in Notion, verbatim apart from obvious slips, with the status the user names (`To Record` when it is ready to shoot), and point `my_script` at that page: from then on it is the script, and the local file is a draft. Copy it into the local `script.md` too, with the slips you fixed listed at the top. Ask whether it goes into `references/voice.md`; never add it unasked.

**Add or update the row in `~/Projects/video-making/INDEX.csv`**: one row per topic, with the paths to the script, the clip and the video, and `hook_type` set to the type picked in step 1, by its name in `hooks.md`. Keeping that file current is part of finishing the job, not an optional extra. Its rules (CRLF line endings, edit in place, never reformat) are in `~/Projects/video-making/CLAUDE.md`.

## The humanizer stack on this machine

- `umanizzatore` and `structural-humanizer` are symlinked into `~/.claude/skills/` from `~/Projects/scrivi-come-un-umano` (public: github.com/andreadorizza/scrivi-come-un-umano). That repo vendors `humanizer` v3.1.0; the desktop plugin `humanizer:humanizer` may be older.
- Catalog changes happen in that repo, not here.
