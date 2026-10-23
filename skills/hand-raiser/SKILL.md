---
name: hand-raiser
description: >-
  Hand-raiser post builder and free-to-paid conversation path. Picks the right type of
  hand-raiser for the offer and audience, writes the post natively for the chosen platform
  using an action that platform allows, writes the DM or comment follow-up sequence that
  turns a raised hand into a real conversation and then a paid yes, and can plan a week of
  organic posts around one offer. Use when the user says "hand raiser", "hand-raiser post",
  "7 days of posts", "organic posts for the week", "who wants this", "comment WORD and I
  will send it", "validate this offer", "what do I say when they DM me", or wants to test
  demand before building.
---

# Hand-Raiser Engine

A hand-raiser is a low-friction post that asks interested people to identify themselves. Platform mechanics come from `../../references/platforms/<platform>.md` (plugin root); read the file for the platform in scope first.

## Step 0: route the brand, then name the basics

1. Name the brand and load its kit per the workspace's brand-routing table. For a client or student there is no kit: use their voice. Never blend brands.
2. Before drafting, state: platform, audience, the action wanted, the CTA, and what done looks like.
3. Read the platform file. If its Verified date is over 60 days old, re-check comment-gating, DM
   automation, and link placement before relying on them.
4. Reel or video hand-raisers default to the person's face and voice with captions. Text-only faceless
   reels are a last resort.

## Pick the hand-raiser type

Ask at most three questions (what is the offer or idea, does it exist yet, how warm is the audience), then
recommend one type and say why.

| Type | Use when | Shape |
|---|---|---|
| **Validation** | The offer does not exist yet | "I'm thinking about building X for Y. If I did, would you want in? Comment WORD." |
| **Asset gate** | There is a useful free thing | "I made X that does Y. Comment WORD and I will send it." Lead with the asset, not the discount. |
| **Beta seats** | First paid round | "Taking N people through X at a beta price in exchange for feedback. Comment WORD for details." Real N only. |
| **Diagnostic** | Audience is problem-aware but not solution-aware | "Which of these is you? 1, 2, or 3. Comment the number and I will tell you the fix." |
| **Waitlist** | Launch is dated | "Doors open DATE. Comment WORD to get first dibs." |
| **Case-study** | There is real proof | "Here is what happened when [real result]. Want the breakdown? Comment WORD." Verified results only. |
| **Poll / opinion** | Cold audience, needs engagement first | A real either-or question whose answer segments the audience. |

**Which action each platform allows (Verified 2026-09-20).** Same hand-raiser type, different action:

| Platform | Use | Don't use |
|---|---|---|
| Instagram | "Comment WORD" with fulfilment ready (run `comment-gate-loop` preflight first) | A gate with no fulfilment plan |
| LinkedIn | "DM me WORD", a poll, a real question, link in the post | "Comment WORD" (named for reduced reach; automation banned) |
| Facebook | A real question, link in the first comment, a Group prompt | "Comment WORD" (demoted as engagement bait), link posts |
| X | "Reply and I'll send it" fulfilled by hand, link in post | Automated keyword DMs |
| TikTok | "DM me WORD" or the bio link if eligible | Comment-to-DM automation (not available in US) |
| YouTube | Pinned comment and description link (long-form; description links need advanced features on), related video or profile links (Shorts) | DMs (none), links in Shorts descriptions |

## Write the post

- Hook in the first line that names the person or the pain. No warm-up.
- One idea. One ask. Where the platform allows a keyword action (see the table above), one keyword, in caps, short, easy to spell, unique to this post. Where it doesn't (LinkedIn comments, Facebook), no keyword: a real question or the link route instead.
- Say exactly what they get and what happens after they comment.
- Native length and format for the platform. Make separate native versions, never a copy-paste across platforms.
- Give one hook plus the runner-up (3 variants on request), and a first comment where the platform file says one helps.
- Comment-gate CTAs lead with the asset. A discount can ride along second.

## Write the follow-up path

The post is 20 percent of the job. Deliver all of this with it:

1. **Public reply** to the comment (short, human, varies so it does not look automated).
2. **DM 1: deliver.** Send what was promised, immediately, no pitch. One genuine question at the end that
   is easy to answer ("what made you grab this?").
3. **DM 2: diagnose** (only if they reply). Reflect what they said. Ask about the situation. Listen for the
   problem the offer solves.
4. **DM 3: bridge.** "Want me to tell you how I help with that?" Permission first, then the offer in 3
   lines, then one clear next step (link, call, or reply YES).
5. **If they go quiet:** one follow-up after 2-3 days that adds value, **sent by hand only**. Never automate it: on Instagram an automated message outside the one private reply and the 24-hour window breaks Meta's messaging rules. Then stop. No chasing, no guilt.
6. **If it is a no or not now:** thank them, tag them in the tracker, move on.

Give the user a simple tracker table to paste: name, platform, date, stage, notes, next step.
The user sends every message or approves the automation. This skill drafts. It does not send.

## Week-of-posts mode ("7 days of posts", "organic posts for the week")

Tie-break with `blow-up-my-social-media`: this skill owns a week built around **one offer** with hand-raisers
in it. A general "what should I post this week" calendar belongs to `blow-up-my-social-media` (series-engine).

One offer, one week, one platform as primary. Each post has a job:

| Day | Job | Type |
|---|---|---|
| 1 | Name the problem | Story or hot take |
| 2 | Teach one thing | Quick win, carousel, or short video |
| 3 | Hand-raiser #1 | Asset gate or diagnostic |
| 4 | Proof or behind the scenes | Real result, real process, or an honest work-in-progress |
| 5 | Belief shift | The myth that keeps them stuck |
| 6 | Hand-raiser #2 | Validation, beta, or waitlist |
| 7 | Personal / connection | Why the person does this. No ask, or a soft one. |

Deliver as a table (day, job, hook, format, CTA, visual idea), then write each post in full. Seven posts is
the default, but if the person can sustain three, write three good ones. Completion beats volume.

## Rules

- No fake scarcity, fake urgency, invented testimonials, or invented numbers.
- Never promise virality, reach, or sales.
- Count real hands. After the post runs, ask for the numbers (comments, DMs, replies, calls, sales) and
  write a short post-mortem: what the numbers say about the offer, not just the post.
- Save the pack where the user keeps working notes (ask once; suggest `~/notes/hand-raisers/YYYY-MM-DD-<slug>.md`).
  Client packs, and **any tracker with real people's names or DM notes**, go to a private folder the user names that is
  not synced and not swept by other automations. CREATED when written, READY only after
  independent review, PUBLISHED only when the user says they posted it.
