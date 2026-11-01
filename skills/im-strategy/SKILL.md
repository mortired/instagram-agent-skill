---
name: im-strategy
description: >-
  Define or revise an Instagram account strategy: audience, goal, positioning,
  content pillars, audience journey, and measures of success. Use for "build my
  Instagram strategy", "who am I creating for", "what should my account be
  about", or a change of direction. Use im-plan for a weekly calendar and
  im-profile for a profile rewrite within an existing strategy.
---

# im-strategy

Turn the user's purpose and available evidence into a compact strategy that
the other skills can use. Write in the user's requested content language.

## Input

Use the conversation and any available `voice.md`, `strategy.md`, `swipe.md`
or audit findings. Shared files live in the user-managed
`~/.chatgpt/instagram/` folder, or arrive as attachments. Do not assume local
file access or memory across chats.

Ask only for missing information that would change the strategy, in one batch:

- What the account is for and what outcome matters over the next period.
- Who it should help, in what situation, and what those people want to do.
- The offer, cause or creative focus, if there is one; selling is optional.
- Real experience, work samples or results the user can show publicly.
- Production capacity, preferred formats, language and topics to avoid.

An account without analytics can still have a strategy. Mark audience beliefs
and proposed goals as assumptions to check. Never invent research, audience
quotes, customer results or a baseline.

## Build the strategy

1. **Choose one primary outcome.** Use the user's goal: relevant discovery,
   returning viewers, community participation, qualified enquiries or another
   concrete outcome. Keep secondary benefits separate. A request for community
   does not automatically become a sales funnel.
2. **Describe the audience's situation.** Name the problem, desired change,
   current obstacle and questions they actually ask. Separate supplied evidence
   from a plausible audience hypothesis; demographics alone are not enough.
3. **Write the account promise.** Explain who benefits, what they get repeatedly,
   and what experience or point of view makes the account useful. Use only
   claims the user can support. Keep the wording usable in a profile bio.
4. **Choose a manageable set of pillars.** Usually three to five is enough.
   For each, give the audience question, the user's evidence or angle, a
   repeatable series idea, two concrete post ideas and a suitable format.
   Fit the volume to production capacity rather than imposing daily posting.
5. **Map the next action.** Show how someone discovers the account, understands
   its value and takes the intended next step. Choose actions appropriate to
   the goal: watch another episode, save, reply, enquire or visit a destination.
   An offer or keyword delivery must exist before content promises it.
6. **Define measurement and review.** For each chosen metric, record its source,
   definition, baseline if known, and review window. Use metrics the user can
   actually obtain. Label an untested target as proposed. If the baseline is
   missing, start with an observation period instead of inventing growth rates.

When revising a strategy, identify which evidence or user decision changed.
Keep the useful parts of the previous direction. Treat new suggestions as
proposals until the user adopts them.

## Output

Produce a concise `strategy.md` with:

- Date, status (proposed or adopted), time horizon and primary outcome.
- Audience, account promise, evidence and open assumptions.
- A pillar table: audience question, angle, series, example posts, format.
- Audience journey, next action and any required destination or resource.
- Production budget, boundaries, success measures and next review trigger.

Keep this brief enough to read before drafting a post. Save to
`~/.chatgpt/instagram/strategy.md` when file access and permissions allow;
otherwise return the complete text for the user to save or attach next time.
Do not claim a save unless it succeeded.

## Handoff

Use available related skills only for the work the user requested:

- [im-plan](../im-plan/SKILL.md) turns the direction into a feasible week.
- [im-series](../im-series/SKILL.md) develops a recurring series.
- [im-profile](../im-profile/SKILL.md) expresses the promise in the profile.
- [im-experiment](../im-experiment/SKILL.md) tests an important assumption.

Pass the relevant brief with the handoff. If a related skill is unavailable,
return that brief without claiming to have invoked it. This skill creates a
strategy; it does not edit the account, schedule posts or send messages.
