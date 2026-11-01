---
name: im-series
description: >-
  Design or continue a recurring Instagram content series with a repeatable
  premise, episode structure, distinct topics, and continuity. Use for
  "create a series", "recurring rubric", "plan the next episodes", or
  "continue this series". Use im-repurpose to extract posts from one existing
  long asset and im-reel to write a single standalone video.
---

# im-series

Build a format the creator can repeat and a viewer can recognise. Each episode
must deliver something useful on its own. Use the user's content language.

## Input

Read available `strategy.md`, `voice.md`, `series.md` and relevant entries from
`log.md`, either attached or in `~/.chatgpt/instagram/`. If there is an existing
series, inspect its actual episodes or supplied summaries before continuing it.

Use the known audience, purpose, production capacity and evidence. Ask only
for missing essentials: the audience question, the material the creator can
reliably supply, and whether this is a finite sequence or an ongoing series.
Do not require a completed strategy document to start.

## Design the series

Define a short series card:

| field | decision |
| --- | --- |
| Series ID and name | a stable identifier and a name the audience understands |
| Promise | the recurring benefit, stated in one sentence |
| Audience question | the specific question this series keeps answering |
| Episode engine | the repeatable source: one case, mistake, question, test or demonstration |
| Format and structure | the medium and sequence of beats or slides |
| Recognition | a recurring segment, phrase or visual element |
| Variation | what changes each time so episodes do not repeat the same lesson |
| Cadence and scope | a sustainable rhythm and, for a finite series, its endpoint |
| Success signal | a measure tied to the promise and available to the user |

For a new series, propose a small pilot batch, usually four to six episodes,
unless the user specifies a different scope. If the available material cannot
support it, reduce the batch or flag what must be collected.

For each episode give a stable ID, an audience question, a distinct angle,
opening idea, promised payoff, evidence or source needed, format and next
action. Reuse a recognisable structure while varying the examples and hooks.
Leave unknown facts as labelled gaps rather than writing invented case studies.

## Continuity

- Check earlier episode IDs and topics before adding new ones. Revisit a topic
  only when there is a new case, level of difficulty or finding.
- Make a finite sequence progress logically, but give each episode enough
  context for someone who sees it first. Deliver its promised answer within it.
- Separate recurring elements from flexible ones. Use `visual.md` if available
  for covers, episode labels and titles.
- Distinguish planned, drafted and published episodes. A finished draft does
  not establish that the user published it. Record publication only when the
  user or an available source confirms it.
- When revising the plan, preserve IDs, published history and unrelated series.
  Explain any change to the premise or remaining order.

## Output

Return the series card and an episode table:

```text
ID | question and angle | opening | payoff | evidence needed | format | status
```

Include the next episode to produce and any missing material. Draft the number
of episodes the user asks for; do not require one-at-a-time approval when they
have already requested a batch.

Maintain the cards and episode tables in `~/.chatgpt/instagram/series.md` when
file access and permissions allow. Otherwise provide the updated text for the
user to save. Do not claim persistence across chats without an accessible file.

## Handoff

Give [im-plan](../im-plan/SKILL.md) the cadence and next episode IDs. Send an
episode brief to [im-reel](../im-reel/SKILL.md),
[im-carousel](../im-carousel/SKILL.md) or [im-story](../im-story/SKILL.md) for
production, and use [im-visual](../im-visual/SKILL.md) for recurring visual rules
when requested. If these skills are unavailable, return the production brief.
Nothing is scheduled or published by this skill.
