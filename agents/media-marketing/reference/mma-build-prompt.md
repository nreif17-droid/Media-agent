# CLAUDE CODE PROMPT — MEDIA MARKETING AGENT (MMA)
*Paste everything below the line into Claude Code, in the `personal-os` repo.*

---

You are building a new agent inside this repo: the **Media Marketing Agent (MMA)**. Follow the same architectural conventions as the existing agents in `agents/` — a `CLAUDE.md` entry point, supporting knowledge files, a log schema, and a logging directory under `logs/`.

## CONTEXT — who this is for

Nolan Reifsteck, 30, relocating to Flagstaff AZ. Instagram: **@Thearchmage712**. Licensed personal trainer. Currently commission-based home-improvement sales at DaBella.

**Daily agenda:**
- Wake ~2:40am
- Stretch, journal, meditate, eat, journal again
- Leave for work — gym early morning
- Office for the sales job, then the day in the field selling
- Home

**Active focuses (only these):** the sales job, daily training, nutrition, Claude Code builds (including a real-estate agent), and this content account.

**Explicitly deprioritized — do not reference as current activity:** a Shaolin discipleship (long-term, ~17 months out, still the plan but not present-day work), an AI automation agency for vacation rentals (idea stage), an energy/grid-interconnection startup (long-term). He also previously ran 1:00–4:00am sales-community calls and daily landscaping — **both are over.** Any content plan built on those is stale.

He doesn't drink and doesn't party.

## TIME BUDGET — floor and ceiling, not a flat cap

This is the constraint that determines whether the whole system survives. Treat it as two numbers, not one:

| | Weekday | Saturday |
|---|---|---|
| **Floor** (guaranteed, worst day of the month) | **30 min** | **90 min** batch block |
| **Ceiling** (good day, when capacity exists) | **90 min** | — |

**The floor is the system.** Every core loop — post, engage, log — must fit inside 30 minutes on a weekday and must never depend on the ceiling existing. Design the baseline against the worst day, because a plan that only works on good days breaks in week three, and missing four days in a row is how people quit permanently.

**The ceiling is upside, allocated in priority order.** When there's extra time, it goes to these in sequence — never to "making the post nicer":

1. **Comment engagement on other accounts** (highest leverage per minute — this is how a small account gets discovered)
2. **DM conversations** — replies, keyword responses, coaching conversations
3. **Extra capture** — filming more raw footage for the Saturday batch
4. **A second post** — only once the first is consistently landing
5. Refinement of existing content — last, and only if 1–4 are done

The agent should ask which mode it's operating in at the start of a session ("floor day or ceiling day?") and scale its output accordingly. It must never assume a ceiling day. If Nolan reports three or more floor days in a row, the agent reduces posting cadence rather than demanding he catch up.

## THE OBJECTIVE

Grow @Thearchmage712 from near-zero to a real audience, and convert that audience into a legitimate coaching-then-digital-product business. The end state is an online fitness/mindset business with a community and a digital product. The near-term state is: find the content angle that works, prove it with data, and reach consistent revenue through 1:1 coaching.

## SOURCE MATERIAL

Two documents should be placed in `agents/media-marketing/reference/` and treated as the initial strategic input. Ingest them, extract the operating rules, and do not silently contradict them — if your research finds them wrong, say so explicitly and explain why:

1. `30-day-instagram-blueprint.md` — positioning, four content pillars (The Forge / The Grind / The Doctrine / The Path), hook system, 30-day reel calendar, metrics
2. `creator-business-model-teardown.md` — analysis of Alex Eubank, Vincent Fischer, Wes Watson, Liam Fitzgerald, Trey Howe; the two distinct business models they run; the shared seven-component system; a phased build sequence

**Important correction to apply on ingest:** the blueprint's pillar examples were written against an older routine (12:40am wake, 1am sales calls, landscaping). Re-anchor them to the current agenda:

- **The Grind** is now the 2:40am wake, the pre-dawn gym session, and the commission sales day in the field. Commission sales is high-stakes and emotionally volatile — rejection, close, dry spell — which makes it *better* material than landscaping was.
- **The Path** is now a longer-horizon thread rather than a near-term countdown. The Shaolin discipleship is real but ~17 months out; treat it as the background arc, not the lead. The lead is what he's building right now.
- **The Forge** stays as-is — training is a daily activity and remains the primary reach engine.

## RESEARCH PHASE — build the knowledge base

Before writing any protocol, research and synthesize. Prefer primary sources, platform documentation, and creators' own stated numbers over secondhand "growth hack" content. Cite what you use. Explicitly flag where the evidence is thin or where the field is just repeating folklore.

Cover:

1. **Instagram distribution mechanics as of 2026** — how reels are ranked and distributed, what the current signals are (watch time, retention curve, shares, sends, saves, comments), how the non-follower reach pool works, what the account's early-days behavior does to long-term reach, whether posting frequency has diminishing returns, and what actually causes suppression.
2. **Hook and retention research** — what measurably holds attention in the first 1.5 seconds, retention-curve shapes and what they indicate, optimal length for this niche.
3. **The creator-coach funnel** — DM keyword funnels, free front doors (Skool, email, webinar), price ladders, conversion rates that are actually realistic at each follower tier.
4. **The five named creators** — reconstruct each one's funnel as precisely as public information allows: what they sell, at what price, through what mechanism, and what their content-to-revenue path looks like. Separate what is verifiable from what is claimed.
5. **The fitness/mindset niche specifically** — saturation, what differentiates accounts that broke through in the last 24 months, and what the audience is currently fatigued by.

Curate all of this into a **static core knowledge base** that doesn't need re-researching every session. Mark anything time-sensitive with a date and a re-check interval.

## WHAT TO BUILD

```
agents/media-marketing/
  CLAUDE.md            # entry point: role, operating rules, commands
  strategy.md          # positioning, pillars, non-negotiables, what this account is and isn't
  knowledge/
    platform.md        # distribution mechanics, ranking signals, dated + re-check intervals
    hooks.md           # hook taxonomy, retention research, worked examples
    funnel.md          # DM keyword funnel, front door, price ladder, realistic conversion math
    competitors.md     # the five creators' funnels, verifiable vs. claimed
  content/
    hook-bank.md       # running bank of hooks, tagged by pillar and pattern, marked used/unused
    pillars.md         # the four pillars with concrete concept lists per pillar
    calendar.md        # current 30-day slate, rolling
  reference/           # the two source docs
  log-schema.md        # exact schema for post logs and weekly reviews

logs/media-marketing/
  posts/               # one entry per post
  weekly/              # weekly review outputs
```

## OPERATING PROTOCOL — what the agent does

Design these as CLI-invocable commands within Claude Code. Nolan works **entirely from his phone**, via the Claude Code mobile Code tab and Obsidian with Git Sync — so every interaction must be short-input, and no command may require him to type more than a few lines.

**`/plan-week`** — Generates the coming week's 7 posts: pillar assignment, hook, shot list, caption, CTA. Must draw only on things he is actually doing that week (ask him what happened / what's scheduled; never invent an activity). Balances pillars per the current performance data, not per a fixed ratio.

**`/log-post`** — Captures a post's results against the schema: date, pillar, hook pattern, format, length, views, non-follower %, average watch %, shares, saves, comments, follows. Minimal typing — accept a terse line and parse it.

**`/review`** — Weekly. Reads the last 7–14 post logs and reports: which pillar earned the highest **follows per 1,000 views** (the primary KPI), which hook patterns produced the best average watch %, what the retention curves imply, and one concrete change for next week. Must state when the sample is too small to conclude anything — do not manufacture insight from four data points.

**`/hook`** — Given a raw thing that happened (a training session, a failure, a 1am call), generate 5 hook variants across different patterns, drawing from the hook bank and marking new ones as unused.

**`/gate`** — The monthly decision gate: reports the month's numbers against targets, names what's working, names what should be cut, and recommends the next phase per the build sequence.

## NON-NEGOTIABLE RULES — encode these in `CLAUDE.md`

1. **Never fabricate.** No invented workouts, results, clients, revenue, or experiences. Content is documentation of what actually happened. If there's nothing to document, say so and suggest he go do something worth documenting.
2. **The credibility filter.** Before any offer or advice-shaped post: *has he actually done this?* If yes, sell it directly. If no, document the attempt instead.
3. **No premature monetization.** Do not help design or launch a high-ticket mentorship or a "how to build a fitness business" offer. The sequence is: proof → 1:1 coaching → low-ticket product → app/community → only then anything that teaches other coaches. The agent should actively push back if asked to skip stages.
4. **Respect the time budget.** The baseline must fit the 30-min weekday floor. The 90-min ceiling is upside only — never a dependency. If a proposed plan requires the ceiling to function, the plan is wrong. Deploy extra time per the priority order in the time budget section, not toward polishing.
5. **Honest metrics.** Report what the numbers say, including when they say the strategy isn't working. Never reframe a bad week as a good one. Small samples get labeled as small samples.
6. **Consistency over brilliance.** If he misses days, the correct response is to reduce cadence to something sustainable, not to demand more.
7. **Flag scope creep.** He runs six other ventures. If content work starts expanding into a seventh full-time job, say so.

## KPIs TO TRACK

| Metric | Role |
|---|---|
| Follows per 1,000 views | **Primary.** The growth KPI |
| Average watch % | Hook grade — under 50% means the first 1.5s failed |
| Shares | Strongest distribution signal |
| Non-follower reach % | Whether new people are being reached at all |
| Saves | Content worth returning to |
| Email captures | The only owned asset |
| Coaching conversations started | Leading indicator of revenue |

## DEFINITION OF DONE

- All files above exist and are populated with real researched content, not placeholders
- `CLAUDE.md` fully specifies the agent's role, rules, and commands
- The knowledge base cites sources and dates time-sensitive claims
- All five commands are specified precisely enough to run
- `log-schema.md` defines a format terse enough to fill from a phone in under 30 seconds
- The hook bank has at least 40 hooks tagged by pillar and pattern
- The calendar has a concrete 30-day slate

## START HERE

1. Confirm you've read both reference documents and state the operating rules you extracted.
2. Ask any clarifying questions you need — but no more than five, and only ones that would change the architecture.
3. Then run the research phase, then build.
