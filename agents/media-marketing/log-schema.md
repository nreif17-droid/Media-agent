# Log Schema

Two schemas: post logs (one file per post, `/log-post`) and weekly reviews
(`/review`). Both are designed to be filled from a phone in under 30
seconds — terse line in, structured file out. `/log-post` and `/review`
parse the terse input themselves; Nolan should never have to hand-type a
YAML block.

## Post log — terse input format

One line, space- or comma-separated, order fixed, `-` for anything
unknown/not yet available:

```
DATE PILLAR HOOK_PATTERN FORMAT LENGTH VIEWS NONFOLLOW% AVGWATCH% SHARES SAVES COMMENTS FOLLOWS
```

Example terse input:
```
8/15 grind ta reel 18s 4200 62 71 9 14 6 11
```

`/log-post` parses this into the stored file below. If a field is `-`,
store it as `null` and note it as pending (views/watch-time data is often
not available same-day — that's expected, not an error).

## Post log — stored format

`logs/media-marketing/posts/YYYY-MM-DD-slug.md`:

```markdown
---
date: YYYY-MM-DD
pillar: forge | grind | doctrine | path
hook_bank_id: <# from content/hook-bank.md, or "new">
hook_pattern: cs | ta | cf | pr | co | rg | da | im
format: reel | story | carousel
length_seconds: <N>
views: <N or null>
nonfollower_pct: <N or null>
avg_watch_pct: <N or null>
shares: <N or null>
saves: <N or null>
comments: <N or null>
follows: <N or null>
follows_per_1000: <computed: follows / views * 1000, or null>
---

<optional one-line note if Nolan adds context beyond the terse line>
```

`follows_per_1000` is computed automatically, never hand-entered — it's
the primary KPI and should never be subject to arithmetic error.

## Weekly review — terse input

Not filled by hand at all — `/review` reads the last 7-14 post logs
directly. Nolan's only input is a one-line prompt if he wants to flag
something not visible in the numbers (e.g. "floor days all week," "sick
Tuesday-Thursday").

## Weekly review — stored format

`logs/media-marketing/weekly/YYYY-MM-DD-week.md`:

```markdown
---
week_of: YYYY-MM-DD
posts_logged: <N>
sample_size_flag: <"too small to conclude" if N < 5>
---

## Best pillar (follows/1,000)
<pillar> — <number>. <Explicitly state if sample too small to trust this.>

## Best hook pattern (avg watch %)
<pattern> — <number>.

## Retention read
<What the shapes of the watch-time curves imply, if resolution allows —
otherwise state plainly that curve-level data wasn't available.>

## Floor/ceiling status
<How many floor vs. ceiling days this week, self-reported or inferred
from post frequency. If 3+ floor days in a row, this section states the
cadence-reduction rule is now active.>

## One concrete change for next week
<Single next action. Never a list.>
```

## KPI reference (full definitions in `CLAUDE.md`)

| Field | Primary use |
|---|---|
| `follows_per_1000` | **Primary KPI.** Growth signal, ★ |
| `avg_watch_pct` | Hook grade — under 50% = hook failed |
| `shares` | Strongest distribution signal |
| `nonfollower_pct` | Whether new people are being reached |
| `saves` | Content worth returning to |
| (tracked separately, not per-post) email captures | Only owned asset |
| (tracked separately, not per-post) coaching conversations started | Leading revenue indicator |

Email captures and coaching-conversation counts don't belong to a single
post — log them as a running note appended to the relevant weekly file
when they happen, terse: `email capture +1` or `coaching convo started —
<one word source, e.g. "DM keyword">`.
