# Knowledge: Clip Construction

*How to actually cut a reel, second by second, so the retention/share
mechanics in `hooks.md` and `platform.md` show up in the finished clip —
not just in theory. Read those two files first; this one is the
production layer on top.*

## The four beats every clip needs

Every reel in this system, regardless of pillar, breaks into four beats.
Skipping one is the most common reason a clip underperforms even with a
strong hook.

1. **0.0–0.3s — the cut-in.** The very first frame, before any words.
   Motion or stakes already visible — never a static shot, never a
   logo/name card, never "hey guys." If the camera was already rolling
   before this frame (per the "leave the camera on" capture method), cut
   in *during* the action, not before it.
2. **0.3–3s — the hook.** The spoken and/or on-screen claim, from the
   hook bank or a fresh `/hook` variant. Text on screen from frame one,
   3-6 words, high contrast. This is the beat that buys the watch time
   that feeds the algorithm (`platform.md`) — everything below only
   matters if this beat works.
3. **3s–~85% — the body.** Whatever actually happened. The one rule that
   separates a clip that holds from one that doesn't: **something has to
   change or escalate**, even in a documentary clip. A flat middle (a
   single continuous action with nothing new to notice) is where the
   retention curve craters, per `hooks.md`'s note on curve shapes. If a
   real clip doesn't have that escalation, cut it shorter rather than
   padding it.
4. **Last 10-20% — the turn and the close.** The payoff the hook
   promised has to actually land here — not resolve two beats earlier and
   coast. End on a deliberate last frame or a hard cut, never a trail-off
   or a fade to nothing. If there's a CTA (DM keyword / email link), it
   lives only in this final beat — never mid-clip, where it interrupts
   the thing that's earning the watch time.

## Caption/text-overlay rules

- On screen from frame one — audio is often off by default (autoplay
  muted), so the hook has to work as pure text too.
- Short: 3-6 words per card, synced to when it's said if there's speech,
  not decorative filler.
- High contrast against the actual footage — check it against both a
  light background scene and a dark one before posting, don't assume one
  style card works everywhere.

## Audio

- **Default to native/raw sound** — the actual sound of the alarm, the
  gym, the truck door. It matches the documentation ethos (`strategy.md`)
  and nothing about trending audio is required for the account's core
  identity.
- Research claims trending audio in the first 3 seconds lifts retention
  (~41%, **[unverified]** per `hooks.md`) — real but unconfirmed effect
  size. Worth trying on **Forge** clips specifically (where raw sound
  matters least), never on **Grind** or **Doctrine** clips where the raw
  audio *is* the proof.

## Pacing

- This account's aesthetic (ascetic, unhurried, per `strategy.md`) does
  not need fast-cut entertainment-style editing. Default to a cut every
  3-5 seconds — a beat every time something changes, not a beat on a
  timer.
- The in-motion cold-open hook pattern (`hooks.md`) pairs naturally with
  one longer unbroken shot at the start rather than a rapid-cut intro —
  let the first cut earn its place instead of assuming faster is better.

## Length

- Default 15-25s per `hooks.md`'s completion-rate data. Only extend past
  30s once a specific reel's `avg_watch_pct` (logged via `/log-post`)
  proves it holds that long — don't extend on instinct.

## Filming logistics, matched to the actual time budget

- Per the 5-min/day capture rule in the original blueprint: shoot the
  raw footage as one continuous take where possible during the activity
  itself — the cut-in/hook/body/close structure above gets built in the
  Saturday edit pass, not live on location. Trying to hit all four beats
  in-camera live costs time the floor doesn't have.
- The Saturday batch (90 min) is where beat 4 (the turn/close and any
  CTA) gets added deliberately — it's the easiest beat to rush, and the
  one most responsible for a clip that "just stops" instead of landing.

## Quick pre-post check

Before logging a post as ready, confirm:
- [ ] First frame has motion or stakes, no static open
- [ ] Hook text is on screen by 0.3s, 3-6 words
- [ ] Something changes or escalates in the body — not one flat beat
- [ ] The close lands the hook's promise, doesn't trail off
- [ ] CTA (if any) is only in the last beat
- [ ] Length is 15-25s unless a logged post has already proven longer
      works for this pillar
