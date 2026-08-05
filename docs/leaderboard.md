---
hide:
  - navigation
---

# xRouteBench Leaderboard

xRouteBench evaluates routers under one quality–cost protocol across five tracks: Generic LLM tasks, memory, vision, time-series, and personalization. The paper evaluates 18 open-weight candidate models (7B–671B) across eight test sets comprising 4,767 test queries.

The values below are transcribed from the accompanying paper's Overleaf source: the main benchmark table, simulated personalized track, Slack deployment study, and multi-agent study.

<div id="xrb-leaderboard"></div>

## Reading the table

- **Family** groups routers by formulation: rule-based baselines, single-turn, multi-turn, and personalized routers.
- **Main track** is the performance-first setting, \((\alpha, \beta) = (1.0, 0.0)\). It covers Generic LLM tasks, two memory sets, three vision sets, and time-series. Rankings shift substantially once cost enters the objective.
- **Personalized track** reports persona-conditioned LLM-judge accuracy. It measures simulated user preference and is not comparable to the main track or live-user study.
- **Real users** reports held-out Slack sessions: 15 users, 40 sessions, and 234 pairwise records. Its target is agreement with actual human preferences.
- **Multi-agent systems** evaluates routing every model call in five coordination topologies. It uses the Generic LLM tasks test split.
- **Formatting** matches the paper tables: the best value in a column is **bold**; the second-best distinct value is <u>underlined</u>. Tied values receive the same mark.

## Updating the data

The table is rendered from `docs/data/leaderboard.json`; no code changes are needed to publish new results. Each row takes a `router` name, a `family`, and a `scores` object keyed by column id. Omit a key to render `—`, or set `"pending": true` to grey out a row whose numbers are still in flight. Update the JSON only from a verified paper table or reproduced evaluation artifact.
