---
name: blow-up-my-social-media
description: >-
  Front door for all organic social work on LinkedIn, X, Instagram, Facebook, TikTok, and
  YouTube (long-form + Shorts). Builds every piece backward from retention to earn one
  outcome: follows, comments, shares, saves, or a sale of merch or a digital asset. Use to
  plan, write, script, package, repurpose, or diagnose social or video content: "write a
  post/reel/short/carousel/thread", "script this", "title and thumbnail", "what should I
  post this week", "content calendar", "content series", "why did this flop", "grow my
  account", "sell my merch", "LinkedIn post", "X post", "hook for this", "blow up my social
  media". Trigger even when no platform is named. Routes to launch-pack, hand-raiser,
  comment-gate-loop, and platform-freshness-loop. Pairs with a brand kit: this skill owns
  platform mechanics and structure, the kit owns voice.
---

# Blow Up My Social Media

The name is the ambition, not a promise. Never guarantee virality, reach, follower counts, or sales. Say "designed to" and show the mechanism. What this skill controls is the inputs: a specific reason to keep watching, a specific reason to act, and a path that works on the platform as it behaves today.

All shared reference files live at the plugin root, two levels up from this skill's base directory: `../../references/`.

## Step 0: Route the brand (never skip)

Load the brand's kit with the Skill tool before drafting. If the brand has no kit (a client, a student, a new project), work from voice samples the user supplies, say that no kit was loaded, and offer to build one (the Tone profile section of `../../references/formats-and-repurposing.md`); never invent a brand voice. If the workspace has a brand-routing table (a CLAUDE.md or AGENTS.md), follow it. If the brand is ambiguous, ask which brand. Never blend brands, including collaborations. The kit wins on voice, banned language, palette, sign-off, and public name. This skill wins on format and platform mechanics.

## Step 1: The job line

Fill it silently when the user gave enough; print it at the top of the deliverable.

```
Brand: ___  Platform(s): ___  Audience: ___
ONE outcome: follow | comment | share | save | sale
Action wanted: ___   CTA: ___   Destination: ___   Success metric: ___
```

One outcome per piece. A piece that tries to earn a follow, a save, and a sale earns none of them. Plan a mix across the week instead (see `../../references/series-engine.md`).

## Step 2: Build backward from retention

Read `../../references/retention-backward.md` and follow its order. The short version: write the ending first, then the payoff, then only the middle beats that earn the payoff, and the hook last, as an honest promise of what the piece delivers. Packaging (cover, title, first line) comes after the hook. A hook written first makes a promise the piece then has to chase; a hook written last describes something that already exists.

## Step 3: Load only the platform file(s) in scope

`../../references/platforms/` holds `linkedin.md`, `x.md`, `instagram.md`, `facebook.md`, `tiktok.md`, `youtube.md`.

Every platform file carries a **Verified** date and tags each claim: **[P]** primary source, **[D]** third-party original data, **[I]** inference or convention. Rules for using them:

- If the Verified date is more than 60 days old, or the claim is tagged [I] and changes the deliverable (a max length, whether a link is clickable, whether a mechanic is allowed), check it with web search first and date-stamp what you found. Then suggest running `platform-freshness-loop`.
- Never upgrade a tag. [I] stays "convention" in anything you tell the user.
- Platform advice from imported prompt libraries, old GPT instructions, or memory is presumed stale until it matches a platform file.

## Step 4: Route the job

| The ask | Go to |
|---|---|
| One finished reel or video going out on several platforms | skill `launch-pack` |
| "Who wants this", validate an offer, "comment WORD" posts, what to say in the DMs, a week around one offer | skill `hand-raiser` |
| A "comment WORD" promise is live and people need their thing | skill `comment-gate-loop` |
| Series, angles, audience questions, what goes in a calendar | `../../references/series-engine.md` |
| Selling merch, downloads, workshops, plugins | `../../references/selling.md` |
| Carousels, threads, repurposing across platforms, trend scans, a tone profile, the 7/30/90-day calendar layout and CSV | `../../references/formats-and-repurposing.md`, then build with Steps 1 to 5 |
| "Why did this flop" | `../../references/flop-autopsy.md` |
| Paid ads | Not this plugin. Use an ad-copy skill; organic rules do not transfer. |
| Anything else (a post, a script, a title + thumbnail) | Build it here, Steps 1 to 5 |

## Step 5: Ship finished pieces

1. **Job line.**
2. **The content, native to the platform.** Hook, body, payoff, button, CTA, plus platform extras (title + thumbnail text, cover text, on-screen text, first comment where the platform file says one helps).
3. **Production notes** only where they change the result. Video scripts use two columns (spoken | on-screen) with timestamps for the hook, each re-hook, the payoff, and the CTA. Default to the person's face and voice with captions; text-only faceless video is a last resort and must be flagged.
4. **Posting notes:** window in the audience's timezone, a reply plan for early comments (it serves the conversation; no platform here has confirmed a first-hour ranking window), link route that actually works on this platform.
5. **What to measure** (retention first, then the outcome metric) and **one next step**.

Repurposing means a native version per platform, never the same caption twice; use the matrix in `../../references/formats-and-repurposing.md`.

Default output is **one finished piece** plus the runner-up hook. The 5 to 10 hooks are working drafts and stay out of the deliverable unless the user asks for a hook bank or variants.

## Quality gate (fix failures, don't list them)

- One outcome, one CTA, and the ending was written before the hook.
- The hook promises exactly what the piece delivers. A competitor could not say it unchanged.
- Every middle beat earns the payoff. Anything that doesn't is cut.
- The CTA is allowed on this platform today. No "comment WORD" on LinkedIn or Facebook (both demote it; see their files). No automation the platform bans.
- Voice matches the loaded kit; its banned language is absent; the public name is the brand's.
- No invented stats, results, testimonials, scarcity, or urgency. Medical, legal, and financial claims are out.
- Every spec is either inside a fresh Verified date or marked "verify current spec".
- Captions on video, alt text on images, on-screen text inside the safe zone.

## Status labels and authority

CREATED when written. READY only after an independent reviewer (a different agent that did not write it) returns PASS against the job line and this gate; otherwise label it UNREVIEWED. PUBLISHED only when the user says they posted it. This plugin drafts. Posting, scheduling, sending DMs, replying to comments, changing a profile, connecting an account, or buying a subscription each need the user's explicit yes in the conversation, every time. One exception: `comment-gate-loop` may send through an automation the user approved for a named campaign and recorded in that campaign's config.

## Scope and stop rules

Do the whole ask: a week of content means every post finished. If a fact is missing, finish everything else and name exactly what is missing. End with one next step. Do not pile on strategy nobody asked for.
