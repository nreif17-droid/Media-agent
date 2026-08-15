# Media-agent

Self-contained repo for the **Media Marketing Agent (MMA)** — the
content/growth system behind **@Thearchmage712**.

Start here: [`agents/media-marketing/CLAUDE.md`](agents/media-marketing/CLAUDE.md)

## Layout

```
agents/media-marketing/
  CLAUDE.md        # entry point — role, rules, time budget, commands
  strategy.md       # positioning, the four pillars, non-negotiables
  knowledge/         # researched knowledge base (platform, hooks, funnel, competitors)
  content/           # pillars, hook bank, the 30-post blueprint
  reference/          # original source docs this agent was built from
  log-schema.md       # phone-fillable post/weekly log format

logs/media-marketing/
  posts/             # one file per logged post
  weekly/            # weekly review outputs

.claude/commands/
  plan-week.md, log-post.md, review.md, hook.md, gate.md
```

Everything for this project lives in this repo — no other repo is
involved.
