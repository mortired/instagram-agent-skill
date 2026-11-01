---
name: im-experiment
description: >-
  Plan or evaluate a focused Instagram content experiment: hypothesis,
  variants, comparison design, metric, observation window, and decision rule.
  Use for "test these hooks", "compare two covers", "does this CTA work",
  "design an experiment", or results from a planned test. Use im-audit for
  broad retrospective analysis of an account's past posts.
---

# im-experiment

Turn a content assumption into a test the user can run and interpret. Write
in the user's language. A test plan is useful even when no results exist yet.

## Input

Use the user's question, available post insights, and relevant `strategy.md`,
`experiments.md` or audit findings. Shared files may be attached or available
under `~/.chatgpt/instagram/`. Ask for missing essentials together:

- The decision the user wants to make and the alternatives they can produce.
- Comparable past posts or a baseline, if available.
- Which metrics are actually available, publishing capacity and review dates.

If asked to evaluate a test, obtain its original plan and actual observations.
If there was no plan, describe the analysis as exploratory and separate any
new hypothesis from the result that suggested it.

## Write the test card before results

1. **Hypothesis.** State the changed element, expected outcome, audience and
   reason: "Changing X may improve Y because Z." Treat the reason as a
   hypothesis unless evidence already supports it.
2. **Variants.** Specify A and B precisely. Change one element when the goal
   is to learn its effect. If several elements change, call it a package
   comparison and do not attribute the result to any one component.
3. **Comparison.** Use genuine random assignment only if an available tool
   supports it. Ordinary posts reach different audiences at different times;
   compare repeated, reasonably matched posts and label the result directional.
   Record differences in topic, offer, format, distribution and post age.
   A before/after change to a profile also has time and audience confounds.
4. **Measurement.** Pick one primary metric tied to the decision and any
   necessary guardrail. Define numerator, denominator, data source and reporting
   window. A hook test needs an available retention measure; raw views alone
   cannot isolate the hook. If a metric is unavailable, narrow the question or
   select a usable measure before testing.
5. **Scope and stopping.** Set a feasible number of comparable posts, a common
   observation age for each, and a review date. Define a practically useful
   improvement and a stop condition before seeing results. Without enough
   baseline data to justify sample size, call this a pilot; no fixed small
   number of posts guarantees a reliable answer.
6. **Decision.** State when to adopt, retain the current approach or collect
   more evidence. Do not keep extending a test only to obtain a preferred
   result or declare a winner after one unusually successful post.

Do not schedule posts or initiate paid tests. Script scores from `hookscore.py`
or `detect.py` can help edit a draft but are not audience experiment outcomes.

## Record observations

Use a stable experiment ID and retain its original plan. Collect:

```text
post ID/URL | variant | published at/timezone | measured at | observation age
primary numerator | primary denominator | guardrail | relevant differences
```

Separate raw counts from rates. Missing data stays missing; a zero denominator
produces an undefined rate. Do not convert unavailable values to zero. Compare
posts at the agreed age, and label immature observations as pending.

## Evaluate

- Show per-post observations and the planned summary, including sample size.
  State how rates were combined; a mean of post rates and a pooled rate answer
  different questions. A viral post must not silently dominate the conclusion.
- For rates, distinguish percentage-point change from relative percentage
  change. Relative change from a zero baseline is undefined.
- Keep the unit of comparison clear. Thousands of views across two posts do
  not become thousands of independently randomised tests of a creative choice.
- Report uncertainty, inconsistent results and plausible confounds. Do not
  claim statistical significance without an appropriate design, assumptions
  and a calculation that was actually performed.
- Return a result of promising, no practical improvement, inconclusive or
  invalid comparison, with the evidence and a concrete next decision. Describe
  organic comparisons as evidence for a next test, not proof of causation.

## Output and handoff

For planning, return the test card and a blank observation table. For review,
return the filled table, calculations, limitations and recommendation. Preserve
other experiment entries when updating `~/.chatgpt/instagram/experiments.md`;
if file access is unavailable, return its updated contents for the user to save.
Only mark a test as run when actual observations have been supplied.

Pass planned variants and measurement timing to [im-plan](../im-plan/SKILL.md).
Use [im-audit](../im-audit/SKILL.md) for wider patterns and
[im-strategy](../im-strategy/SKILL.md) when the user wants to revise direction
after reviewing the evidence. Use these skills only if available and relevant
to the requested work. The user runs the publishing and supplies the results.
