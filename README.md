# The Instagram agent skill

Seventeen ChatGPT skills that run an Instagram account. Free, MIT, no signup, no
API key, nothing to connect.

One of them writes your Reels off 26 hook formulas and scores the hook before
you waste a take on it. One goes and finds the reels that are actually working
in your niche and ranks them by how far each beat its own account. One writes
the caption and shows you exactly what the feed shows before the "... more".
One scores your profile out of 100 and rewrites what lost points. One plans the
week.

And one is the humanizer, which is the reason the rest are usable. It strips
the em dashes, the slop vocabulary and the invisible watermark characters out
of a draft, then scores what is left against a five-check panel before you ever
see it.

**Nothing gets posted until you say yes.** These skills write. You post.

## Use in ChatGPT

Paste a skill's `SKILL.md` into ChatGPT, or attach it with the supporting files
from its folder, and ask ChatGPT to follow it. Keep the Python scripts and JSON
resources together when using a session that can run them.

The `/im-*` labels below are prompt shortcuts for the workflows, not built-in
ChatGPT commands. For an installed skill, use ChatGPT's `@` skill selector.
See the [official skills guide](https://learn.chatgpt.com/docs/build-skills).

`plugin.json` packages the `skills/` directory for distribution. The source
files in this folder have not been installed or published automatically.

The `~/.chatgpt/instagram/` paths below are a user-managed folder for this pack,
not a built-in ChatGPT configuration directory. If ChatGPT cannot access local
files, attach the relevant `voice.md`, `swipe.md`, `log.md` or `plan.md` instead.
The strategy, series, experiment and visual skills use the same folder for
`strategy.md`, `series.md`, `experiments.md` and `visual.md` respectively.

Then spend ten minutes on [templates/voice.md](templates/voice.md). Copy it to
`~/.chatgpt/instagram/voice.md` and fill it in, or send ChatGPT three of your own
reels and say "write my voice.md from these". Every skill reads that file. It
matters more here than on other platforms, because you have to say the words
out loud.

## The seventeen

| command | what it does |
| --- | --- |
| [/im-strategy](skills/im-strategy/SKILL.md) | Defines the audience, account promise, goals, content pillars, next action and success measures in `strategy.md`. |
| [/im-series](skills/im-series/SKILL.md) | Builds recurring series with a repeatable structure, distinct episode ideas, stable IDs and continuity in `series.md`. |
| [/im-experiment](skills/im-experiment/SKILL.md) | Plans and reviews focused content tests with defined variants, metrics, observation windows and decision rules in `experiments.md`. |
| [/im-visual](skills/im-visual/SKILL.md) | Defines consistent colours, typography, covers, titles and Story templates in `visual.md`; creates assets when requested and tools are available. |
| [/im-reel](skills/im-reel/SKILL.md) | One idea into a Reel. Three hooks from [26 formulas](skills/im-reel/hooks.json), scored, then the script, the on-screen text and a timed beat sheet. |
| [/im-viral](skills/im-viral/SKILL.md) | Goes and finds what is working in your niche, ranks it by multiple over each account's own median, names the formula, writes the swipe file. |
| [/im-caption](skills/im-caption/SKILL.md) | The caption, linted. Shows you the 125 characters the feed actually shows before the tap. |
| [/im-carousel](skills/im-carousel/SKILL.md) | Swipe posts. The cover that earns the swipe, slide copy, and the 1080x1350 files. |
| [/im-story](skills/im-story/SKILL.md) | The daily story sequence, which sticker does which job, and the DM funnel that starts with them moving first. |
| [/im-profile](skills/im-profile/SKILL.md) | Scores your profile against a [12-part rubric](skills/im-profile/rubric.json) out of 100, then rewrites in fix-first order. |
| [/im-plan](skills/im-plan/SKILL.md) | The week. What to post, which format, when, and the 10 accounts to engage with. |
| [/im-human](skills/im-human/SKILL.md) | The humanizer. Two scripts that actually run. See below. |
| [/im-comment](skills/im-comment/SKILL.md) | Comments on other people's posts. Nine types, picked by what the post actually is. Never "🔥🔥🔥". |
| [/im-reply](skills/im-reply/SKILL.md) | The thread under your own post. Sorts into keyword / lead / substance / question / support / noise, then writes in that order. |
| [/im-dm](skills/im-dm/SKILL.md) | The keyword delivery, the first message, the collab pitch, and the two follow-ups. Two. |
| [/im-repurpose](skills/im-repurpose/SKILL.md) | One video, podcast or newsletter into a week of reels and carousels that each stand alone. |
| [/im-audit](skills/im-audit/SKILL.md) | Post-mortem on what you already posted. Ranks by outlier multiple and sends per reach, not views. |

Start with [/im-strategy](skills/im-strategy/SKILL.md) when the account needs a direction. [/im-series](skills/im-series/SKILL.md)
develops recurring formats and [/im-visual](skills/im-visual/SKILL.md) sets their appearance. [/im-plan](skills/im-plan/SKILL.md)
uses those briefs to build the week; the existing writing skills produce the
individual posts. [/im-audit](skills/im-audit/SKILL.md) reviews results, and [/im-experiment](skills/im-experiment/SKILL.md) helps test
an uncertain finding. Each skill can also be used independently with the
context supplied in the chat. The four new skills require no Python scripts.

## The six tools that actually run

No dependencies, no network, nothing uploaded. They run on your machine, on
your text.

### Hooks

```bash
python3 hookscore.py hooks.txt              # rank your options
python3 beats.py script.txt --target 30     # time it before you shoot it
```

```
HOOK RANKING
==============================================================================
->  85.6 STRONG  Nobody tells you that your first 30 reels are supposed to f...
        weakest: SPECIFICITY (75)
    81.4 STRONG  I lost $18,000 because of one missing contract.
        weakest: ADDRESS (70)
    54.4 OK      Stop scrolling if you want to grow on Instagram in 2026 🔥
        weakest: STAKES (70)
        dealbreaker: Opens with "stop scrolling". Asking for attention proves
                     you have not earned it.
     9.6 WEAK    Hey guys, today I wanted to talk about content strategy
        weakest: FRONTLOAD (0)
        dealbreaker: Greeting. Nobody came to the feed to be greeted.
```

`beats.py` estimates how long each line takes to say, stacks them into
timecodes, and flags the four things that kill a Reel in the edit: a hook that
runs past three seconds, a beat long enough for the viewer to leave, a run of
lines with nothing concrete in them, and no loop back to the first line.

```
BEAT SHEET  ·  73 words  ·  ~26.6s at 165 wpm  ·  target 30.0s
========================================================================
  0:00.0   2.9s  HOOK    I lost $18,000 because of one missing contract.
  0:02.9  14.6s  MID     Here is the exact clause I now put in every single...
                         ^ 14.6s on one beat
  0:17.4   2.9s          Section 4. Payment on delivery, not on approval.
  0:20.4   2.9s          Approval is a feeling. Delivery is a date.
  0:23.3   3.3s  CTA     That one word change is worth $18,000 to me.
------------------------------------------------------------------------
  - Beat 2 runs past 4s. Either split the line or change what is on screen
    inside it. A static frame is where people leave.
  - Loops: the last beat repeats "$18,000" from the hook. Second watches are
    free reach.
  - 3.5s under target. Either add 9 words or shoot it short. Short is usually
    right.
```

### The caption

```bash
python3 caption.py caption.txt --keywords "client contracts,freelance pricing"
```

Instagram gives a caption about 125 characters in the feed and hides the rest
behind a tap. Almost every caption that fails, fails there. So the first thing
this prints is that window, as a box, the way a scrolling stranger reads it:

```
  WHAT THE FEED SHOWS
  +------------------------------------------------------+
  | I lost $18,000 because of one missing clause in a    |
  | contract, and the worst part is that I had read the  |
  | thing twice before I si                              |
  +-------------------------------------------- ... more +

  PASS  LENGTH            389 / 2200 characters
  WARN  FIRST LINE        133 characters, so it gets cut at 125 mid-thought
  PASS  HOOK IS CONCRETE  2 numbers or names in the visible window
  PASS  HASHTAGS          3 tags: #freelance #contracts #agencyowner
  PASS  ONE ASK           one call to action: comment a keyword
  WARN  SEARCH TERMS      1/2 present. Missing: client contracts
```

It enforces the current hashtag cap, which is **five per post**, not thirty.
Instagram cut it on 18 December 2025.

### The humanizer

```bash
python3 humanize.py draft.txt --report      # clean it, show every change
python3 detect.py draft.txt                  # score it, five checks
python3 detect.py before.txt after.txt       # prove the delta
```

**What comes out automatically:**

- **Invisible characters.** Zero-width spaces and joiners, word joiners, soft
  hyphens, byte-order marks, Unicode tag characters, invisible separators,
  non-breaking and narrow spaces. Your keyboard does not make these. They
  survive copy-paste and they are invisible in every editor you own.
- **Typography.** Em dash to comma, en dash to hyphen, curly quotes to
  straight, ellipsis to three dots, and the orphaned punctuation that leaves.
- **The lexicon.** 154 stock words and phrases with plain-English replacements.
  The last block of it is Instagram-specific: "stop scrolling", "in today's
  video", "follow for more", "tag someone who needs this", "the algorithm
  loves", "run don't walk". It lives in
  [`slop.json`](skills/im-human/slop.json) and it is meant to be edited.

**What gets flagged instead of fixed:** "It's not just X, it's Y", rule-of-three
triads, the video preamble, emoji bullet lists, three shouted words in a row,
hashtag walls, reflex follow bait, uniform sentence length. Changing the shape
of a sentence needs judgement, so those come back for a rewrite rather than
getting mangled by a regex.

Run against a caption written to be as bad as possible:

```
  BURSTINESS    ###################.....  78.4
  SPECIFICITY   #############...........  53.6    3.4 concrete markers per 100 words
  SLOP DENSITY  ........................   0.0    20 stock terms, 23.0 per 100 words
  FINGERPRINT   ################........  68.7    1 em dash
  VOICE         #################.......  70.0    9 structural tells
  ------------------------------------------------------------
  HUMAN SCORE   ########................  32.5   FLAGGED
```

After `humanize.py`, with the flagged structures still unrewritten:

```
  HUMAN SCORE   ###################.....  79.7   PASS    (+47.2)
```

### The swipe file

```bash
python3 swipe.py captured.tsv --out ~/.chatgpt/instagram/swipe.md
```

Raw views are not evidence. A 2,000,000-follower account doing 400,000 views
had a quiet Tuesday. A 4,000-follower account doing 400,000 views found
something. `swipe.py` ranks on the multiple over each account's own median,
names the hook formula, and prints what separates the top third from the
bottom third.

```
SWIPE FILE  ·  4 reels  ·  4 accounts  ·  baseline: account median
==============================================================================
    60.0x  hook  57  #9  The Steal              @c                 180,000
           "steal this four line follow up it took me two years"
    37.5x  hook  86  #3  Nobody Tells You       @a                 412,000
           "nobody tells you that your first 30 reels are supposed to flop"
     1.3x  hook  13  -   unclassified           @b               1,200,000
           "in this video I am going to show you my morning routine"
```

## What I actually measured, which is the part worth reading

I did not want to publish a hook scorer on the claim that it feels right, so I
tested it. The corpus is **74 real short-form hooks**: the first three seconds
of the auto-caption track from the top eight and bottom eight performing shorts
on each of five channels, view counts from 931 to 550,000.

They are YouTube Shorts rather than Reels, because Instagram does not hand you
view counts you can collect without logging into somebody's account, and
scraping it would violate the Terms this repo tells you not to violate. The
hook grammar is the same and the sourcing is public. That is a real limitation
and it is stated here rather than buried.

**Three results, two of them uncomfortable:**

**1. It catches bad hooks well.** Against ten hooks written deliberately badly,
AUC 0.83, and nine of the ten scored below the median of the real corpus. If
your hook opens on a greeting, a preamble or nothing concrete, this tells you.

**2. It does not pick winners.** Separating a good creator's hits from that
same creator's misses: **AUC 0.56, where 0.50 is a coin flip.** Of the five
checks, only SPECIFICITY separated the bands meaningfully, by 60 points of
median. STAKES and ADDRESS had identical medians in both bands, which means on
this corpus they measured nothing.

So the honest use is: kill the obviously weak hooks before you shoot them, then
trust your own retention graph. Nothing that reads text can tell you which of
two decent hooks will travel, because that is decided by your face, your edit,
your audio and who Instagram shows it to.

**3. The formula classifier was broken and the test is what caught it.** The
`match` regexes in `hooks.json` were written off my own templates, and they
named **8%** of real hooks. People do not speak in templates. Rewriting them
against actual transcribed speech took it to **49%**, and four formulas went
into the set because they kept appearing and were not there: Contrarian Flip,
The Statistic, The Reveal, Someone Else's Result, plus The Superlative. On the
other 51% it abstains, which is correct: a lot of short-form is podcast clips
that have no hook formula at all.

One fixed bug worth naming: `SPECIFICITY` only counted digits, so "zero
dollars" and "three marketing books" scored as having nothing concrete in them.
Spoken hooks say their numbers out loud.

If you re-run this on a bigger or cleaner corpus and get a different answer, I
would rather know. The measurement script is not in the repo because it depends
on `yt-dlp`, but the method is four lines and is written out in
[/im-viral](skills/im-viral/SKILL.md).

## The fine print, which is the honest part

**These skills do not post to Instagram.** There is a real Content Publishing
API for Professional accounts, and it needs a Meta developer app, a linked
Page, a long-lived token and app review, which is not a thing a skill can hand
you. Everything else people use to automate posting, commenting, following or
DMing is browser automation or a third-party tool, and both violate
[Instagram's Terms of Use](https://help.instagram.com/581066165581870) and get
accounts action-blocked. So every skill here ends the same way: a copy-ready
block, and you post it. That is not a limitation bolted on afterwards, it is
the design, and it is why the approval gate is real rather than a setting.

The one exception is keyword auto-replies in DMs, which Instagram supports
through its own tools and approved partners, and which only fire after somebody
comments first. [/im-dm](skills/im-dm/SKILL.md) says where that line is.

**[/im-viral](skills/im-viral/SKILL.md) reads, it does not scrape.** Ten accounts, a dozen reels each, at
human speed, with you driving your own browser. It never asks for your password
and never logs in as you. Automated collection at volume is the thing that gets
accounts restricted, and a crawler is not what this is.

**The five detection checks are local heuristics, not detector APIs.** They are
modelled on the signals public detectors key on and they run entirely on your
machine. They are not GPTZero, Originality, Copyleaks, Winston or Turnitin,
they do not call those services, and they cannot promise those verdicts. Fixing
what they measure tends to move those numbers, because they are measuring the
same underlying things. That is the whole claim. Nobody can honestly sell you
"undetectable", and anybody who does is selling you something.

**The invisible-character pass is real and it is narrow.** It removes the
zero-width and format characters that end up in generated text and survive a
copy-paste. That is a genuine, checkable fingerprint. It is not a claim about
defeating a cryptographic watermarking scheme, and this repo does not make one.

**Nothing here fabricates.** No invented metrics, clients or outcomes go under
your name. If a draft needs a number you have not given, it comes back with
`{{your number}}` in it and a flag, every time.

**Platform numbers go stale.** The hashtag cap moved from 30 to 5 in December
2025 while this repo was being written, and the linter had the old number in it
until the fact got checked. If something here contradicts what Instagram is
doing when you read it, Instagram is right.

## Files

| file | what it contains |
| --- | --- |
| [skills/im-reel/hooks.json](skills/im-reel/hooks.json) | 26 hook formulas: template, example, on-screen line, what it is for, how it gets ruined, and a match regex. |
| [skills/im-reel/hookscore.py](skills/im-reel/hookscore.py) | The five-property hook panel. |
| [skills/im-reel/beats.py](skills/im-reel/beats.py) | Script to timed beat sheet. |
| [skills/im-caption/caption.py](skills/im-caption/caption.py) | The truncation preview and the caption linter. |
| [skills/im-human/slop.json](skills/im-human/slop.json) | The lexicon: 154 terms, 18 invisible classes, 16 tells. |
| [skills/im-human/humanize.py](skills/im-human/humanize.py) | The three cleaning passes. |
| [skills/im-human/detect.py](skills/im-human/detect.py) | The five-check panel. |
| [skills/im-viral/swipe.py](skills/im-viral/swipe.py) | Outlier ranking and formula classification. |
| [skills/im-profile/rubric.json](skills/im-profile/rubric.json) | The 100-point profile score. |
| [templates/voice.md](templates/voice.md) | Your voice profile. Fill this in first. |

## Credit

Made by Konstantin Davidenko, [joe_mort8123](https://www.instagram.com/joe_mort8123).

## License

MIT. Take it, change it, ship it.
