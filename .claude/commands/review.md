---
description: Weekly MMA review — reads the last 7-14 post logs, reports what's working
---

Read `agents/media-marketing/log-schema.md` and
`agents/media-marketing/CLAUDE.md` first.

1. Read every file in `logs/media-marketing/posts/` from the last 14
   days (7 if that's all that exists).
2. **If fewer than 5 posts are logged, say so explicitly and refuse to
   draw pillar/hook conclusions from them** — rule 5 in `CLAUDE.md`,
   "honest metrics," applies directly here. You can still report raw
   numbers, just don't rank pillars or patterns as "winning" on a sample
   that small.
3. If the sample supports it, compute and report:
   - **Follows per 1,000 views by pillar** — the primary KPI. Which
     pillar is highest, and by how much (not just which one is first).
   - **Average watch % by hook pattern** — flag any pattern averaging
     under 50% as a failing hook, per `knowledge/hooks.md`.
   - **What the retention curves imply**, if per-post detail is
     available (early drop-off = hook failure; late drop-off = weak
     ending) — otherwise state plainly that curve-level data wasn't
     captured this week, don't guess.
4. **Ask about floor/ceiling status for the week** if not already noted,
   and check for 3+ consecutive floor days — if found, state that the
   cadence-reduction rule (`CLAUDE.md` rule 6) is now active and say what
   the reduced cadence should be for next week.
5. Give exactly **one concrete change for next week** — not a list. Per
   `CLAUDE.md` rule 5, if the honest read is "nothing's working yet, stay
   the course a bit longer because the sample's too small," say that
   instead of manufacturing a change.
6. Write the result to
   `logs/media-marketing/weekly/YYYY-MM-DD-week.md` in the exact format
   from `log-schema.md`.
7. Output to Nolan: the same content, compressed to what fits a phone
   screen without scrolling much — lead with the one concrete change,
   not buried at the bottom.
