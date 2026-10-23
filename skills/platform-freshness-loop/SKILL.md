---
name: platform-freshness-loop
description: >-
  Keeps the plugin's platform facts current. Re-verifies the claims in
  references/platforms/*.md (LinkedIn, X, Instagram, Facebook, TikTok, YouTube) against
  primary sources and dated third-party data, proposes edits with sources, and updates each
  file's Verified date only after the user approves. Use when the user says "refresh the
  platform files", "are the social rules still current", "what changed on Instagram/LinkedIn/
  TikTok/X/YouTube/Facebook", "check the algorithms", "platform freshness", when any platform
  file's Verified date is more than 60 days old, or when a /loop or /schedule run names
  platform-freshness-loop. Intended to run about monthly.
---

# Platform Freshness Loop

Social platforms change faster than any skill file. Stale advice is worse than none because it sounds confident. This loop is why the plugin can say "verified" with a date.

Files: `../../references/platforms/*.md`. State: `~/.claude/loops/platform-freshness-loop/run-log.md`.

## Each run

1. Read the run log and each platform file's **Verified** date. Work oldest first. If the user named a platform, do only that one.
2. For each file, list the claims that change a deliverable: ranking signals, max lengths and ratios, hashtag caps, link behavior, what is demoted, comment-gate and DM automation rules, eligibility thresholds, selling routes, view-counting and monetization rules. Re-check every [I] claim that has been sitting as a default.
3. Verify with web search and fetch. Source order: the platform's own engineering blog, newsroom, help center, policy and developer docs, open-source repos, and named staff statements. Then third-party **original data** with a stated sample size. Blog opinion is not a source. One research pass per platform; run platforms in parallel when agents are available.
4. For each claim record: CONFIRMED, STALE, CONTESTED, or UNVERIFIABLE; what is true now in one sentence; URL; publication date. Never invent a number or a source. If a page won't load, say so.
5. Write the proposed edits as a diff-style list per file: old line, new line, source. Keep the tags honest: [P] primary, [D] third-party data or reporting, [I] inference. Never upgrade a tag without the source to back it.
6. **Stop for approval.** Show the list. Apply only what the user approves, then set the file's Verified date to today. Files with no changes still get the new date, with "re-verified, no change" in the log.
7. Have a different agent spot-check the applied edits against the cited sources (PASS or NEEDS REVISION). No reviewer available: label the run UNREVIEWED in the log.

## Output

Top of the report: "Biggest changes a strategist would get wrong", max 8 bullets across platforms, each with its date. Then the per-file lists. Then one next step.

## Stop rules

- Bound the search to claims that change a deliverable. Do not rewrite strategy.
- One fallback wave per platform. After that, mark what stayed UNVERIFIABLE and finish.
- Append a dated entry to the run log: platforms checked, claims changed, claims left unverifiable, review status.
