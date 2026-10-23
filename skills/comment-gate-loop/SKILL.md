---
name: comment-gate-loop
description: >-
  Fulfilment loop for any "comment WORD and I'll send it" or "DM me WORD" promise, on any
  campaign and any keyword. Runs a preflight before the post goes live (is the gate allowed
  on this platform, does the sending route actually work right now), then on each run finds
  new keyword comments, sends the promised asset where an approved automation exists, builds
  a manual checklist where it doesn't, and keeps a ledger so nobody is messaged twice or
  missed. Use when the user says "run the gate loop", "check my comments for WORD", "fulfil
  the comment gate", "who commented", "did anyone comment on the launch posts", "set up a
  comment gate", or when a /loop, /schedule, or cron run names comment-gate-loop.
---

# Comment-Gate Loop

A gate is a promise. Every unanswered keyword comment is a broken promise in public, and on Instagram the window to fix it closes 7 days after the comment. This loop exists so that never happens quietly.

Platform rules live in `../../references/platforms/`. Read the file for each platform in the campaign; if its Verified date is over 60 days old, re-check the gate and DM rules before relying on them.

## State

One folder per campaign: `~/.claude/loops/comment-gate-loop/<campaign-slug>/`

- `config.md` — brand, keyword, the promised asset and its link, start and end date, live post URLs per platform with lane (auto or manual), the DM template, the public nudge reply, the manual paste text, the **expected run interval**, and an **approved automations** table (platform, tool, what it may send, the date the user approved it). No row in that table, no auto lane.
- `processed-comments.md` — the ledger: platform, comment id or handle, date, how fulfilled.
- `run-log.md` — dated entry per run.

The ledger holds real people's handles. Keep it in this folder; never copy it into notes that sync or get swept by other loops. If `config.md` is missing, ask for the keyword, asset link, and post URLs before doing anything.

Message templates use the brand's public name and voice from its kit. Never a legal name.

## Preflight (before the post goes live, and again on the first run)

1. **Is a comment gate allowed here?**

   | Platform | Lane |
   |---|---|
   | Instagram | Gate OK. Automated private reply is possible: one message, within 7 days of the comment; open conversation only after they reply. |
   | TikTok (US) | No comment-triggered automation. Use "DM me WORD" or the bio link. DM automation exists for Business accounts only, and only if the user has set it up. |
   | LinkedIn | **No comment gate.** The pattern is named for reduced reach and automation is banned. Use "DM me WORD", a real question, or the link in the post. Manual only. |
   | Facebook | **No comment gate.** Requests for comments are demoted. Put the link in the first comment. Manual only. |
   | X | Manual only. Automated keyword DMs conflict with X's automation rules. |
   | YouTube | No DMs. Long-form: pinned comment and first description line (description links need advanced features on). Shorts: links in descriptions and comments are not clickable, so use the related-video link or channel profile links. |

   If the draft post uses a gate in a "no" lane, say so and offer the replacement wording before it is published.
2. **Does the sending route work right now?** Call your connected scheduler's account list once. An auth error here is a stop-the-launch finding: tell the user immediately, in the first line of output, that the automated lane is down and every comment will need manual fulfilment until it is fixed.
3. **Is the promised asset real and reachable?** Open the link. A gate to a dead link is worse than no gate.
4. **Send one test** to the user's own account if they approve it.

Report preflight as PASS or FAIL per platform. Do not mark a campaign live on a FAIL without the user saying so.

## Each run

1. Read the run log, config, and ledger. **Schedule-gap check:** if the last run is older than twice the expected interval, open the output with `SCHEDULE GAP`, the dates nothing ran, and which comments are at risk of passing their 7-day window. **Manual check-in:** open every run by asking which manual fulfilments the user has done since the last run, and record them. If today is past the end date: do one final sweep, write the closing summary, tell the user to remove the schedule, and **stop**. A loop that keeps firing on a closed campaign is a defect; say so loudly on every post-close run.
2. **Auth check first.** If the scheduler returns an auth error, do not just log it. Put it at the top of the output, send a notification if the session can, and switch every platform to the manual lane for this run. Count how many days remain before the oldest known comment passes its 7-day window.
3. **Auto lane** (only platforms preflight marked auto, only automations the user approved): list comments since the last run; keep those that are not the author, contain the keyword case-insensitively, and are not in the ledger. Send the one private reply with the template. Never retry a private reply the ledger already records; the one shot is spent. Optionally post the public nudge. Write each ledger line immediately after its send, not at the end.
4. **Manual lane:** list each live post URL with its last-checked date and the exact paste text. In a scheduled or headless run, send the user a notification with the posts to check and the paste text; a checklist nobody sees fulfils nobody. The user reports back who they handled; record those in the ledger the same way. If nothing has been reported back for two runs, say so at the top.
5. **Totals:** seen, auto-fulfilled, manually fulfilled, pending. Anything pending over 24 hours goes at the top, flagged. Anything within 48 hours of its 7-day window goes above that.

## Stop rules

- Success: every new keyword comment is fulfilled or on the checklist, ledger and log updated. Zero new comments is a valid success.
- A send fails: log it, don't retry a private reply, move that person to manual.
- Tools unavailable: produce the manual checklist from config alone and say so. Never skip a run silently.
- Hard cap 50 automated sends per run. More than that, stop and let the user decide whether to switch to a link in the comments.
- Two consecutive runs with dead auth: recommend pausing the schedule until the login is fixed, because each run is wasted.

## Authority

Sending a DM, replying to a comment, connecting an account, and creating or removing a schedule are the user's decisions. The one standing exception to ask-every-time: the loop may send through an automation listed in `config.md`'s approved automations table, for this campaign only, using only the templates in `config.md`. Anything else, including a changed template or a new platform, needs a fresh yes.

## After each run

Append the dated entry: per platform — new comments, auto-sent, flagged manual, pending, failures, auth status. Advance the last-run timestamp **only after a successful comment read**; on an auth failure or tool outage hold it where it is and log `gap open since <timestamp>` so the next good run re-sweeps the whole gap. Confirm every send has a ledger line. At campaign close, write totals by lane and one line on what to change next time.
