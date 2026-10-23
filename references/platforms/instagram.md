# Instagram

**Verified: 2026-09-20.** Tags: [P] primary source, [D] third-party original data or reporting, [I] inference or convention. Adam Mosseri's original posts and the Help Center could not be opened; rows that depend on them are relayed by secondary sources and tagged [D].

## How distribution works now

- The three named signals: **watch time, likes per reach, sends per reach.** Sends weigh a bit more for reaching non-followers, likes a bit more for followers. [D1] Saves as a "quality signal" and a "3-second hold" metric have no primary source; treat both as useful diagnostics, not ranking facts. [I]
- **Originality is enforced.** Since 2026-04-30 the aggregator penalty covers photos and carousels too; accounts that mainly repost lose recommendation eligibility. A watermark, a speed change, or a credit does not make it original. [D2] Clean exports only, no other app's watermark.
- Captions and hashtags feed Search. [P3] Public professional accounts are indexed by Google and Bing by default since 2025-07-10 (opt-out in Privacy). [D4] Write the first caption line like a search result. On-screen text being indexed: unverified.
- Teen accounts default to PG-13 (2025-10), which limits strong-language content reaching under-18s. [P5]

## Formats

- **Reels.** Must be **3 minutes or less to be recommended** to non-followers. [P3] Peak reach rate at 30 to 60 seconds (5.60%) versus under 30 (5.20%) across 140k business Reels. [D6] The old "7 to 30 seconds" rule is stale. Visual + verbal hook in the first second, on-screen hook text for muted viewers, cover frame carries the hook.
- **Carousels.** Up to 20 slides. The grid previews at **3:4**; 1080x1440 is the size the grid doesn't crop. 4:5 still posts. [D7] Cover slide is a hook, slide two delivers immediately, last slide is the CTA.
- **Stories** reach existing followers. The link sticker remains the clickable link outside the bio. [I]
- **Hashtags.** A cap of 5, rolling out gradually; fewer and targeted; they classify, they don't add reach. Hashtag following was removed. [D8]
- New since 2025-08: reposts and the Friends tab, **linked Reels series** (use this for every series), "Your Algorithm" topic controls. [P9][P10]

## Small-account reality

Trial Reels are reported to need 1,000+ followers and Subscriptions 10,000; both come from secondary write-ups with no primary page opened. [I] Under 1,000, the levers are linked series, reposts, collabs, and comment-to-DM. Broadcast channel eligibility is unverified (guides disagree: no minimum, about 1,000, or 10,000); check the account.

## Cadence and timing

Posting 3 to 5 times a week is associated with more than double the follower growth of 1 to 2; weeks with no posts are associated with follower loss (2.1M posts, 102k accounts). [D11] Timing is "the cherry on top": midweek, Thursday 9am, Wednesday noon and 6pm (9.6M posts). [D12] The account's own Insights beat any benchmark.

## Comment-gates and DMs

Allowed. The Private Replies API permits **one** message within **7 days** of the comment; free conversation opens only after the person replies, inside the 24-hour window. [P13] ManyChat states it is an official Meta Business Partner (not checked in Meta's directory). [D14] "Highest-converting mechanic" has no data behind it; don't say it. A reach penalty for "comment WORD" on Instagram is unverified (Facebook is different, see its file). A gate with no working fulfilment is a broken promise: run `comment-gate-loop` preflight before the post goes live.

## Selling

The Shop tab is gone and native US checkout was phased out in 2025. Product tags send buyers to **your own website**, which is required. [D15] Clickable caption links are a test limited to Meta Verified. [D16] Practical routes: bio link with the current offer on top, Story link sticker, comment-to-DM with the link, broadcast channel for drops. Bio-link details: unverified.

## Sources

- D1 dataslayer.ai/blog/instagram-algorithm-2025-complete-guide-for-marketers (relays Mosseri, 2025-01-22)
- D2 techcrunch.com/2026/04/30/instagram-restricts-reach-of-content-aggregators-in-new-crackdown
- P3 creators.instagram.com/blog/tips-for-improving-your-reach (page dated 2023-05-31, edited since)
- D4 ppc.land/instagram-content-becomes-searchable-on-google-starting-july-10 (2025-07-10)
- P5 about.fb.com/news/2025/10/instagram-teen-accounts-pg-13-ratings (2025-10-14)
- D6 socialinsider.io/blog/instagram-reels-statistics (2026-06-24)
- D7 recurpost.com/instagram-scheduler/instagram-post-size-guide (relays Mosseri, 2025-05)
- D8 socialmediatoday.com/news/instagram-implements-new-limits-on-hashtag-use/808309 (2025-12-18)
- P9 about.fb.com/news/2025/08/new-instagram-features-help-you-connect (2025-08-06)
- P10 about.instagram.com/blog/announcements/reels-algorithm-control (2025-12-10)
- D11 buffer.com/resources/how-often-to-post-on-instagram (2025-08-13)
- D12 buffer.com/resources/when-is-the-best-time-to-post-on-instagram (2026-07-14)
- P13 developers.facebook.com/documentation/business-messaging/instagram-messaging/features/private-replies (undated)
- D14 manychat.com/blog/manychat-official-meta-business-partner (undated)
- D15 ppc.land/meta-phases-out-facebook-and-instagram-shops-checkout-by-august-2025
- D16 petapixel.com/2026/03/16/instagram-begins-testing-clickable-links-in-post-captions
