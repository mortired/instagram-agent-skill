---
name: im-visual
description: >-
  Define or refine a consistent Instagram visual identity for Reel covers,
  carousels, video titles, and Stories: palette, typography, layout, imagery,
  and reusable template specifications. Use for "visual style", "make my
  covers consistent", "brand my Instagram", or "design a template system".
  Use im-carousel to produce a single carousel within an established style.
---

# im-visual

Create a visual guide the user can reproduce with their actual tools. Use the
user's content language, and test typography with text in that language.

## Input

Inspect available brand guidelines, logos, fonts, sample posts and references,
plus `strategy.md`, `voice.md`, `series.md` or an existing `visual.md`. Shared
files may be attached or available under `~/.chatgpt/instagram/`.

Ask only for missing choices that affect the work: what must stay, what should
change, which formats matter, and which design or editing tools the user uses.
Preserve an established identity unless the user requests a change. If there
is no identity yet, propose a small number of directions with a concrete
palette, type treatment and cover concept, then recommend a starting point.
Unselected directions remain proposals.

If reference images cannot be viewed, ask for an accessible image or description
and state what remains unverified. Do not claim to have inspected a grid or a
design file based on its filename or an inaccessible link.

## Define reusable rules

| element | specify |
| --- | --- |
| Colour | exact values and roles: background, text, accent, secondary use |
| Typography | heading/body roles, weights, size hierarchy and fallback fonts |
| Layout | alignment, margins, text width and position of the handle or episode label |
| Imagery | subjects, framing, lighting, treatment and when to use real footage |
| Titles and subtitles | line length, line breaks, placement and readable backgrounds |
| Recognition | a repeatable visual detail shared across formats |
| Variation | what may change between series and what stays consistent |

Check that proposed fonts support the user's language and are available in the
intended editor. Flag any unverified availability or licence instead of claiming
the font is installed or free to use. Start with the user's existing assets
where possible.

## Specify the templates

Cover the formats the user actually needs. A useful starting set is a Reel
cover, carousel cover and body slide, and Story frame. For each template give:

- Canvas dimensions and intended viewing surface.
- Layout zones, text hierarchy, image placement and variable fields.
- One concrete example using supplied content or clearly labelled sample copy.
- Guidance for long titles, missing photos and episode numbers.
- Export format and a short assembly recipe for the user's editor.

Use the requested canvas or a suitable working size, such as 1080x1350 for a
portrait slide and 1080x1920 for vertical video. These are design starting
points, not assertions about every current placement. Check current platform
guidance or a supplied preview before promising a specific crop or safe area.

Keep important text away from interface overlays. Check legibility at phone
and thumbnail sizes, contrast between text and background, and long words in
the actual content language. Do not encode an essential distinction only by
colour. Give video subtitles a readable backing when the footage varies.

## Deliver at the available level

If the user requests a guide, provide the guide. If they also request rendered
examples or editable assets, use the available design, image or rendering tools
and inspect the produced result. Provide actual output files only when created.
With no rendering tools, return layout specifications and assembly instructions
and clearly identify them as specifications.

Use references to identify transferable properties such as spacing, contrast
or framing. Build the user's own treatment rather than reproducing another
account's logo or pretending sample assets belong to the user.

## Output and handoff

Return a compact `visual.md` containing the chosen or proposed direction,
reusable rules, template specifications, examples and unresolved asset needs.
Separate verified decisions from unchecked fonts, crops or rendering details.
Save it under `~/.chatgpt/instagram/` when file access and permissions allow;
otherwise return its contents for the user to save or attach later.

Pass relevant rules to [im-carousel](../im-carousel/SKILL.md),
[im-reel](../im-reel/SKILL.md), [im-story](../im-story/SKILL.md) and
[im-profile](../im-profile/SKILL.md). Coordinate episode labels with
[im-series](../im-series/SKILL.md) when available. This skill does not upload
assets or change the account's profile or posts.
