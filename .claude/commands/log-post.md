---
description: Log a post's results (one terse line) against the MMA schema
argument-hint: [terse line, or paste multiple]
---

Read `agents/media-marketing/log-schema.md` before doing anything else.

The user will give you one terse line (or several, one per post) in this
order, space- or comma-separated, `-` for unknown:

```
DATE PILLAR HOOK_PATTERN FORMAT LENGTH VIEWS NONFOLLOW% AVGWATCH% SHARES SAVES COMMENTS FOLLOWS
```

If the message you receive (`$ARGUMENTS`) already contains this, parse it
directly — don't ask for it again. If it's missing or incomplete, ask for
just the missing terse line, not a form.

For each line:

1. Parse into the stored schema fields. Compute `follows_per_1000` =
   `follows / views * 1000` yourself — never leave it for Nolan to
   compute, and never let a hand-entered value override the computation.
2. Look up the hook used, if identifiable, against
   `agents/media-marketing/content/hook-bank.md` and mark that row `used
   (DATE)` if it isn't already.
3. Write `logs/media-marketing/posts/YYYY-MM-DD-slug.md` in the exact
   format from `log-schema.md`. Slug: pillar + short descriptor, e.g.
   `2026-08-15-grind-alarm.md`.
4. If a field is `-`, store `null` and note in your reply that it's
   pending — same-day view/watch-time data is often incomplete, that's
   expected, not an error.
5. Confirm back in one line: date, pillar, and the computed
   follows/1,000 — nothing longer.

Never editorialize on a single post's performance here — that's `/review`'s
job, working across multiple posts. This command's only output is
confirmation that the log was written correctly.
