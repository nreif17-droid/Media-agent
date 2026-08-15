# Knowledge: Hooks & Retention

*Compiled Aug 2026. Re-check interval noted per section.*

## What the first 1.5–3 seconds actually needs to do

The blueprint's "1.5 seconds" framing and the researched "first 3 seconds"
window are the same claim at different granularity — both point at the same
mechanic: viewers decide whether to keep watching almost immediately, and
that decision is what feeds the top-ranked signal (watch time, see
`platform.md`). The hook isn't a creative-writing exercise, it's the input
to the algorithm's most important variable.

**[aggregated/unverified, various]** Concrete retention levers found in
research, roughly in order of how well-supported they are:

1. **A specific, on-screen claim naming who this is for and what's at
   stake** — outperforms a vague opener. "Specific hook that calls out who
   you're talking to and what problem you're solving" is the single most
   repeated finding across sources.
2. **A face in frame within the first 3 seconds** — claimed ~35% retention
   lift. [unverified exact number, directionally plausible — faces are a
   known attention-grabbing stimulus in general attention research, not
   specific to Instagram]
3. **Motion or a stakes-bearing action in frame one** — matches the
   blueprint's own rule. No opening on a static shot or a name card.
4. **Text on screen from frame one** — removes the need for audio to land
   the hook (autoplay is often muted), and gives the algorithm's own
   caption/OCR systems something unambiguous to classify the content by.

## Retention curve shapes

- **[aggregated]** Average watch time across reels generally lands 6–10
  seconds regardless of total length — meaning a 45-second reel and a
  15-second reel often hold viewers for a similar *absolute* time, which
  makes the 15-second reel's *percentage* retention look much better.
- **[aggregated]** Short reels (≤15s) show materially higher completion
  rates (~72%) than longer ones (~46%). This is the strongest evidentiary
  case for the blueprint's "under 30 seconds until you find what works,
  then extend" rule — if anything, the evidence argues for testing even
  shorter (10-15s) before extending.
- **A retention curve that craters in the first 2-3 seconds** = hook
  failure, regardless of what happens after. **A curve that holds flat
  through 80%+ then drops at the very end** = the payoff is landing but
  the ending is weak (no clear closing beat / CTA). These are different
  problems requiring different fixes — `/review` should distinguish them
  when watch-time data is available at that resolution, and flag when it
  isn't.

## Hook taxonomy (patterns, not templates — vary the wording every time)

These map to the six patterns in the blueprint plus two added from research:

| Pattern | Mechanism | Best pillar fit |
|---|---|---|
| **Countdown/stakes** | Names a deadline or consequence | The Path |
| **Time anomaly** | Names an unusual hour/timestamp | The Grind |
| **Confession** | Admits a failure or lapse, present tense | The Doctrine |
| **Process reveal** | "Day N of X" — a running count | The Forge |
| **Cost statement** | Names what something actually costs (time/money/pain) | The Grind, The Path |
| **Refusal of the guru frame** | Explicitly disclaims false authority | The Doctrine |
| **Direct address** *(added)* | Names the specific viewer this is for, in the first line | Any — use when a pillar's usual pattern is exhausted |
| **In-motion cold open** *(added)* | No spoken hook at all — text overlay only, action already underway when the clip starts | The Forge — pairs with the "motion in frame one" retention lever above |

**Patterns to avoid** (per blueprint, holds regardless of pillar): "Most
people will never…", "The 1% do this…", "If you're watching this, it's a
sign…" — these read as borrowed-authority phrasing from creators with an
established results-based claim to make. Nolan doesn't have that claim yet
(see credibility filter, `CLAUDE.md`), so these patterns read as
performance rather than documentation, on top of already being clichéd.

## Length guidance

- Default to 15–25 seconds. Only extend past 30s once a specific reel has
  proven it holds attention that long (average watch % data will show it).
- This tightens the blueprint's "under 30 seconds until you find what
  works" to a harder floor, based on the completion-rate data above.

## Re-check interval

Retention-curve and length data: 6 months. Hook taxonomy itself doesn't
need re-checking — it's a structural pattern list, not a platform fact.
