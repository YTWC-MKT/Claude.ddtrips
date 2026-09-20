# Status

## 2026-09-13
- Confirmed Windsor connectors via `get_connectors`: `google_my_business` account
  `locations/17253298120475111002` = "Deep Dive Trips" ✅, `facebook_organic` account
  `1068114356395128` = "Deep Dive Trips" ✅ — both match the standing config, no changes by the
  account owner.
- Attempted a real GMB media read (`get_data` on `google_my_business`, fields incl.
  `media_category`, `media_format`, `media_view_count`) to make today's photo/video gap list
  specific instead of generic. Got the plan-limit error: *"reads are paused because you have 14
  accounts connected and your Free plan includes 1 account."* Same known blocker already listed
  in TASKS.md under "Blocked on you" — not retried, logged here per the standing rule and moved on
  with a framework-based deliverable instead of real counts.
- Completed Day 4 (GMB photo/video gap list + shot list) — see
  `day4-gmb-photo-video-gap-list.md`. Nothing published (not a GMB-post task, and
  `business-info.md` still doesn't exist).
- `business-info.md` still not present in the repo — still the single biggest unlock per
  TASKS.md; Day 5 (next up: second week of GMB posts) will again need placeholders unless it's
  added before the next run.

## 2026-09-14
- Re-confirmed Windsor connectors via `get_connectors`: `google_my_business` account
  `locations/17253298120475111002` = "Deep Dive Trips" and `facebook_organic` account
  `1068114356395128` = "Deep Dive Trips" — both unchanged, no read attempted today since Day 5
  isn't a data-driven task.
- `business-info.md` still not present. Completed Day 5 (Week 2 GMB post calendar + 8 Q&A seed
  questions) as a placeholder draft — see `day5-gmb-posts-week2-qa.md`. Every post and every Q&A
  answer still has at least one bracketed placeholder (trip names, locations, prices,
  cancellation policy, group ratios), so nothing qualifies for auto-publish under the standing
  rule. Nothing published.
- Next run: Day 6 (2-week Instagram/Facebook content calendar) is next up under Phase 2 — will
  also need `business-info.md` or client input for real specifics, and per the hard rule,
  Instagram/Facebook posts stay draft-only regardless.

## 2026-09-15
- `business-info.md` still not present in the repo. Completed Day 6 (2-week Instagram/Facebook
  content calendar, reels-first, 14 posts with captions + shot lists) as a placeholder draft — see
  `day6-instagram-facebook-content-calendar.md`. Cross-referenced Day 4's shot list and Day 5's
  GMB Q&A so the three don't drift once real specifics land. Did not query Windsor today — Day 6
  isn't a data-driven task, and Instagram/Facebook writes are never executed by this routine
  regardless of Windsor status (hard rule, not a data gap). Nothing published or scheduled
  anywhere; per the hard rule Instagram/Facebook stay draft-only even once placeholders are filled.
- Next run: Day 7 (SEO landing-page copy draft for top 3 destination/course pages) is next up
  under Phase 2 — will need either the live site URL structure/CMS access (listed under "Blocked
  on you") or will proceed as a generic-template draft against assumed page types if that's still
  not provided.

## 2026-09-16
- `business-info.md` and site URL structure/CMS access both still not present/provided. Completed
  Day 7 (SEO landing-page copy for 2 destination-page archetypes + 1 certification-course page,
  full title tags/meta descriptions/body copy/FAQ/schema markup/internal linking, wired to Day 3's
  GA4 click events and Day 2's CTA-placement findings) as a placeholder draft — see
  `day7-seo-landing-page-copy.md`. No real destination or course names exist anywhere in the repo
  yet, so page topics themselves are bracketed placeholders, not just prices/dates. Did not query
  Windsor today — Day 7 isn't a data-driven task and doesn't touch GMB/Facebook. Nothing
  published; this task type (website copy) can never auto-publish regardless of placeholders,
  since this routine has no CMS/site access.
- Next run: Day 8 (Local directory audit — TripAdvisor, JustDial, Sulekha, etc. — + NAP
  consistency list) is next up under Phase 2.

## 2026-09-17
- Re-confirmed Windsor connectors via `get_connectors`: `google_my_business` account
  `locations/17253298120475111002` = "Deep Dive Trips" and `facebook_organic` account
  `1068114356395128` = "Deep Dive Trips" — both unchanged. Attempted a real `get_data` pull on
  `google_my_business` (location title, address, phone, website, category, maps/place IDs) to
  ground today's NAP audit in the actual live listing instead of placeholders. Got the same
  plan-limit error as 2026-09-13: *"reads are paused because you have 14 accounts connected and
  your Free plan includes 1 account."* Not retried, per the standing rule — moved on with a
  framework-based deliverable.
- `business-info.md` still not present. Completed Day 8 (local directory audit + NAP consistency
  list) as a framework draft — see `day8-local-directory-audit.md`. Includes a "Step 0" master NAP
  record template, a priority-ranked directory list (Google Business Profile, TripAdvisor,
  Thrillophilia, JustDial, Facebook About tab, Bing Places, Sulekha, IndiaMART, Holidify,
  Trawell.in, GetYourGuide/Viator, LinkedIn, Apple Business Connect, Yellow Pages India, state
  tourism board, PADI/SSI locator) with real claim/submission URLs and a claiming workflow, plus a
  blank tracking table ready to fill in once real NAP facts exist. Flagged two additional inputs
  needed beyond business-info.md: which state/coast Deep Dive Trips operates from (for the
  regional tourism board listing) and whether it holds a PADI/SSI certifying-body affiliation (for
  the dive-specific locators). Nothing submitted to any directory — this is audit/framework only.
- Next run: Day 9 (Partnership outreach list — hotels/resorts/dive shops — + outreach email
  template) is next up under Phase 2.

## 2026-09-18
- Found and fixed a repo-hygiene issue before starting today's task: this session's git HEAD was
  detached and 6 commits ahead of local `main`, while `origin/main` on GitHub was already at the
  same commit as HEAD (7f6ce10, Day 8) — a stale local ref cache made it briefly look like Days
  2-8 had never reached GitHub. Re-fetched and confirmed `origin/main` already had everything; no
  data was actually at risk, but noting it here in case the detached-HEAD state recurs.
- `business-info.md` still not present. Completed Day 9 (Partnership outreach list + email
  templates) as a framework draft — see `day9-partnership-outreach.md`. Covers 7 partner
  categories (hotels/resorts, non-competing dive shops for cross-referral, tour operators,
  water-sports operators, wedding/underwater photographers, corporate/MICE — deferred to Day 14,
  backpacker hostel chains) with real, runnable methods for finding actual prospects (PADI/SSI
  locators, Google Maps searches, JustDial/IndiaMART, Instagram hashtags), an outreach priority
  sequence, 5 ready-to-send email templates (hotel pitch, dive-shop cross-referral, water-sports
  in-person message, hostel-chain partner inquiry, follow-up), and a blank tracking table. Did not
  query Windsor today — this task doesn't touch GMB/Facebook/ads. Nothing sent to anyone; per the
  hard rule all outreach/messaging stays human-sent regardless of placeholder status.
- Next run: Day 10 (Blog/long-tail SEO topic list) is next up under Phase 2 — needs Ahrefs data
  once that plan issue clears, else will proceed manually per TASKS.md's own note.

## 2026-09-19
- Checked Ahrefs before starting Day 10: `subscription-info-limits-and-usage` and
  `keywords-explorer-matching-terms` (query "scuba diving india", country `in`) both returned
  `{"error": "Insufficient plan"}` — the Ahrefs API key on this account isn't on a tier that
  includes Keywords Explorer/usage data. This is a separate blocker from the Windsor GMB/FB
  14-accounts-on-Free-plan issue (different platform, different account) — logging it here as its
  own item, not retried, per the standing rule. Did not query Windsor today since Day 10 doesn't
  touch GMB/Facebook.
- `business-info.md` still not present. Completed Day 10 (blog/long-tail SEO topic list) manually
  per TASKS.md's own fallback note — see `day10-blog-seo-topics.md`. 13 fully-briefed topics
  (keyword, intent, title/meta, outline, internal links, CTA) across two tiers: 8 top-of-funnel
  informational posts needing zero Deep Dive Trips-specific facts, and 5 comparison/mid-funnel
  posts blocked only on one new input — which certifying body (PADI/SSI/both) Deep Dive Trips is
  affiliated with, now needed by three separate deliverables (this file, Day 7's course page, Day
  9's dive-shop outreach). 4 more destination-specific topics listed for later sequencing, blocked
  on business-info.md. Includes a suggested 12-week publishing calendar wired to Day 7's landing
  pages for internal linking and Day 3's GA4 click events. Nothing published — this routine has no
  CMS/blog access, so this task always ends in a draft file.
- Next run: Day 11 (Meta ads campaign structure + creative brief) is next up under Phase 3 — ad
  spend/targeting always stays draft-only regardless of placeholder status per the hard rule, so
  this will be a full draft file rather than anything executed.

## 2026-09-20
- Re-confirmed Windsor connectors via `get_connectors`: `google_my_business` account
  `locations/17253298120475111002` = "Deep Dive Trips" and `facebook_organic` account
  `1068114356395128` = "Deep Dive Trips" — both unchanged. Noted `googleanalytics4` now also
  shows a connected `ddtrips.in` account (id `540396303`) that wasn't previously flagged as
  connected — worth revisiting for Day 3's GA4 event verification once the Free-plan account cap
  is resolved.
- Attempted a real `get_data` pull on `facebook_organic` (page name, fan count) to ground today's
  Meta ads audience/budget brief in real page-size data. Got the same plan-limit error as prior
  days: *"reads are paused because you have 14 accounts connected and your Free plan includes 1
  account."* Not retried, per the standing rule — moved on with industry-standard starting
  budgets instead of real account-size-informed ones.
- `business-info.md` still not present. Completed Day 11 (Meta ads campaign structure + creative
  brief) as a framework draft — see `day11-meta-ads-campaign-brief.md`. Covers a 4-campaign
  account structure (retargeting, trial-dive prospecting, certification prospecting, seasonal/
  urgency), a real starting budget baseline (₹1,200-1,500/day total, phased rollout
  recommendation starting with just Campaign 2), a lookalike + interest-stack audience plan wired
  to Day 3's pixel events, and 4 full creative concepts (hooks, captions, CTA buttons) — 3 of the
  4 need only business-info.md facts to become launch-ready, the seasonal concept needs a
  specific upcoming trip to exist first. Nothing executed — hard rule, ad spend never
  auto-publishes regardless of placeholder status.
- Next run: Day 12 (Google Ads keyword list + campaign structure — Search + Performance Max) is
  next up under Phase 3.
