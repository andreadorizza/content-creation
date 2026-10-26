# Hook catalogue

The hook step in `SKILL.md` writes one candidate per type below, all on the same idea, ranks them and lets the user pick. The type is the **angle** on the idea, and it decides what the rest of the video becomes. That is why the hook is chosen before anything else is written.

**The shapes are examples.** A type has many shapes. Write the shape that fits the idea in front of you, and invent a new one when none fits, as long as the angle stays the same (the user, 2026-10-26).

Sources: seven types (shock, comprehensive, common mistake, comparison, question, negative, tutorial) from a list the user pasted on 2026-10-26, each backed there by a viral example of 6.4M–32M views (origin not recorded). `notizia` comes from Saraev's reels (`~/Projects/video-making/reference/PATTERNS.md`: 7 of his 11 single-tool reels) and is the type of 13 rows in `INDEX.csv`.

## One idea, many videos

The user's example, on getting a six-pack. Same topic, a different video each time:

| Type | Hook |
|---|---|
| Shock | "You Can Get a 6-Pack While Still Eating Ice Cream Every Day" |
| Comprehensive | "Here is Every Ab Exercise You Need to Get a 6-Pack" |
| Common mistake | "Doing Sit-Ups Won't Get You a 6-Pack" |
| Comparison | "Lifting vs. Cardio, What Will Get You a 6-Pack Faster?" |
| Question | "Is it Possible to Get a 6-Pack in 6 Weeks?" |
| Negative | "You Will NEVER Get a 6-Pack if You Do This One Thing!" |
| Tutorial | "Here is a Week of Workouts Designed to Help You Get a 6-Pack" |

## The types

The name in `code` is the `hook_type` value for `INDEX.csv`.

### `shock`

A claim that sounds impossible or wrong, which the video then proves.

- Shapes: "Puoi fare X anche senza Y." · "Ho fatto X senza scrivere una riga di codice." · "L'AI di Google è razzista. Guarda." (`bias-google`)
- Honest when the proof is on screen within the first beats. If the claim needs a caveat to stay true, it is not a shock hook.
- The video: the first body delivers the proof, by 5–10 s; the rest is how.

### `completo`

Everything the viewer needs for one goal, in one video.

- Shapes: "Ecco tutti gli strumenti che ti servono per X." · "Tutto quello che ti serve per X, in 60 secondi." · "Gli unici N X di cui hai bisogno per Y."
- Honest when the list really covers the goal. The goal must be concrete ("per sapere se la tua app si fa bucare"), never a category ("gli strumenti AI che ti servono"): content-principles §5 explains why a category kills curiosity.
- The video: the set skeleton.

### `errore`

The viewer is doing the usual thing, and it does not get them what they want.

- Shapes: "X non ti porta a Y." · "Se per Y usi ancora X, stai perdendo tempo." · "Non usare X finché non hai Y."
- Honest when the mistake is common and the subject really fixes it. It points at the viewer's habit, never at a flaw of the subject (*Only the positive side*).
- The video: the first body names the mistake and why it fails, then comes the fix.

### `confronto`

Two named options, one goal.

- Shapes: "X o Y: cosa ti porta prima a Z?" · "Lascia perdere X, usa Y." · "Ho dato lo stesso compito a X e a Y."
- Honest when both options are real and named, and the comparison was actually made, by the user or by a named source.
- The video: one body per option, and the payoff is the verdict.

### `domanda`

A question the viewer wants answered.

- Shapes: "Si può fare X in Y?" · "E se ti dicessi che…?" (voice) · "Stufo che…?"
- Honest when the video answers it on screen and the answer is worth the wait. The viewer must be the one holding the question, not someone on screen (content-principles §4).
- The video: the question is the open loop, and the payoff answers it.

### `negativo`

A warning, sharper than `errore`: the one thing that will stop the viewer for good.

- Shapes: "Non otterrai MAI X se fai questa cosa." · "Smetti subito di fare X." · "Questo errore ti costa X."
- Honest when the stake is real and the subject removes it. Same limit as `errore`: the viewer's habit, never the subject's flaw.
- The video: the first body names the thing; the rest is the way out.

### `tutorial`

The method, promised as an outcome.

- Shapes: "Ecco il sistema per X." · "Così fai X in Y minuti." · "Tre passi per X."
- Honest when the outcome can be shown on screen.
- The video: the *problema → sistema* skeleton.

### `notizia`

It just came out, and it changes something for the viewer.

- Shapes: "È appena uscito X." · "Google ha appena rilasciato X." · "Da oggi puoi X." (Paper2agent)
- Honest when it is actually new. A stale *appena* is the fastest way to lose trust in this niche.
- The video: the default skeleton. The bodies carry what came out, what changes for the viewer, and what it opens up.

## Old values in `INDEX.csv`

Rows written before 2026-10-26 use the six feeling types the skill had then. Leave them as they are, and read them like this when you look for a past video:

| Old value | Closest type now |
|---|---|
| `divieto`, `divieto implicito` | `errore` or `negativo` |
| `sostituzione` | `confronto` |
| `notizia` | `notizia` |
| `promessa` | `tutorial` |
| `dolore` | `domanda` |
| `provocazione` | `shock` |
