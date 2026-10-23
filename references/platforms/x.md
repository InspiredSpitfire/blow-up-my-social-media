# X

**Verified: 2026-09-20.** Tags: [P] primary source, [D] third-party original data, [I] inference or convention. help.x.com blocked automated reads, so tier prices and limits below are secondary. Re-verify before relying.

## How distribution works now

X publishes its ranking weights. They multiply the *predicted probability* of each action, not raw counts. From the open-source repo (`home-mixer/params/param.rs`, last commit 2026-09-18) [P1]:

| Predicted action | Weight |
|---|---|
| Share via copy-link | 20.0 |
| Reply between mutual followers | +15.0 boost |
| Reply | 5.0 |
| Quote | 5.0 |
| Share via DM | 5.0 |
| Follows the author | 4.0 |
| Share | 2.0 |
| Repost | 1.0 |
| Like | 0.5 |
| Click | 0.4 |
| Opens link | 0.2 |
| Dwell | 0.05 |
| Not interested / Block / Mute / Report | -43.2 / -31.2 / -58.8 / -234 |

Out-of-network posts are scaled by 0.75. An author's second and later posts in one viewer's feed decay (0.5, floor 0.25). [P1]

What that means [I]:
- Write posts people **send to someone** or **reply to**. Likes barely count.
- Replies with mutuals are the biggest lever a small account has. Build mutuals on purpose and reply to them first.
- One strong post beats a burst. Bursts decay against each other.
- Anything that earns a mute or a report costs more than a good post earns. No spam tactics, no reply-guy volume.

## Premium

Median impressions per post: under 100 for free accounts, about 600 for Premium, over 1,550 for Premium+ (18.8M posts, 71k accounts). Correlation, per Buffer, not proven causation. [D2] Web prices are roughly $3, $8, and $40 a month (secondary). Buying a subscription is the user's decision; state the data and stop.

## Links

X's head of product said links no longer need to go in replies, and X says the penalty ended over a year ago. [D3] Third-party data still found a 0% median engagement rate on free accounts' link posts since March 2025. [D2] Default: post the idea natively and make it stand alone; when the click matters, put the link in the post and test it against a no-link version. Don't state either position as fact.

## Formats and limits

- 280 characters free, 25,000 on Premium (secondary). [D4] Video limits and vertical-feed status: unverified.
- Articles opened to all Premium subscribers 2026-01-07. [D5] Threads vs long posts vs Articles: no performance data found. Given author-diversity decay, default to one strong post. [I]
- Hashtags are banned in ads (2025-06-27). [P6] Organic: 0 to 1. [I]

## Comment-gates, DMs, and automation

The API is pay-per-use: $0.005 per post read, $0.001 per owned read (includes mentions), $0.010 per DM event read, $0.015 per post or DM created, $0.20 per post containing a URL. [P7] X's automation rules require the user to initiate the interaction, and AI reply bots need X's approval (read from a snippet, not the page). [I] Default: **manual fulfilment**. "Reply WORD" works only as a prompt for a conversation the person does by hand.

## Earning and selling

Revenue sharing was replaced by Original Content Rewards on 2026-09-08: Premium, 500 verified followers, and 500k impressions from verified users in 90 days; original content only. [D8] No native merch or digital-product feature found. Selling on X means a link out. [I]

## Sources

- P1 github.com/xai-org/x-algorithm/blob/main/home-mixer/params/param.rs (commit 2026-09-18)
- D2 buffer.com/resources/x-premium-review (2025-10-02)
- D3 ppc.land/x-drops-year-old-link-penalty-musk-tells-zuckerberg-on-platform (2026-07-29)
- D4 typecount.com/blog/twitter-character-limit (2026)
- D5 ppc.land/x-doubles-creator-revenue-pool-and-offers-1m-for-top-article-but-why (2026-01)
- P6 x.com/elonmusk/status/1938156166724653197 (2025-06-26)
- P7 docs.x.com/x-api/getting-started/pricing (undated; launched 2026-02)
- D8 techcrunch.com/2026/08/08/x-replaces-misaligned-revenue-sharing-program-with-original-content-rewards
