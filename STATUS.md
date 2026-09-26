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

## 2026-09-21
- Found and fixed a repo-hygiene issue before starting today's task: local `main` was stale
  (pointing at the Day 9 commit) while this session's `HEAD` was already 2 commits ahead
  (Day 10, Day 11) and detached — same class of issue logged on 2026-09-18. Fetched origin,
  confirmed `origin/main` already had both Day 10 and Day 11 (nothing was actually unpushed this
  time), then reset local `main` to match and re-attached HEAD. No data lost.
- Re-confirmed Windsor connectors via `get_connectors`: `google_my_business` account
  `locations/17253298120475111002` = "Deep Dive Trips" and `facebook_organic` account
  `1068114356395128` = "Deep Dive Trips" — both unchanged. Did not attempt a `get_data` read
  today since Day 12 doesn't need GMB/FB data (it needs Google Ads + Ahrefs data instead).
- Checked Ahrefs before starting: `subscription-info-limits-and-usage` again returned
  `{"error": "Insufficient plan"}` — same blocker as Day 10, not retried per the standing rule.
  No real keyword volume/CPC/competition data was available, so Day 12's keyword list is
  prioritized by commercial intent only, with no invented metrics.
- `business-info.md` still not present. Completed Day 12 (Google Ads keyword list + campaign
  structure) as a framework draft — see `day12-google-ads-keyword-campaign.md`. Covers a
  5-campaign account structure (Brand, Certification, Trial/Fun Dive, Location/Generic Search,
  plus a Performance Max campaign sequenced to launch only after Search has 2-4 weeks of real
  conversion data), keyword lists by intent tier with match types, a negative-keyword list,
  starting daily budgets (~₹1,600/day Search-only at launch, ~₹2,000/day once PMax turns on),
  and full RSA headline/description copy for the Brand, Trial Dive, and Certification ad groups
  (rest templated, same pattern, ready once business-info.md lands). Wired conversion tracking to
  Day 3's three GA4 events and location targeting to the same coast/state input already blocked
  in Day 8/9/10. Nothing executed — Windsor doesn't even show a connected `google_ads` account
  for this business, and ad spend never auto-publishes regardless per the hard rule.
- Next run: Day 13 (WhatsApp broadcast list setup plan + referral program design) is next up
  under Phase 3.

## 2026-09-22
- Found and fixed the same repo-hygiene issue logged on 2026-09-18/21 again: this session's
  checkout started with `HEAD` detached at the same commit as `origin/main` (`c3fdbe4`, Day 12)
  while the local `main` branch ref was still 3 commits stale (pointing at Day 9). Checked out
  `main` and fast-forwarded it to `origin/main` before starting today's work — no data lost, no
  force-push needed.
- Did not query Windsor today — Day 13 (WhatsApp broadcast list + referral program) isn't a
  connected read/write platform in this setup, so there was nothing to verify against live data.
- `business-info.md` still not present. Completed Day 13 (WhatsApp broadcast list setup plan +
  referral program design) as a framework draft — see `day13-whatsapp-referral-program.md`.
  Covers: a WhatsApp Business App vs. API-platform decision with an India-specific
  recommendation, the Meta opt-in/24-hour-window compliance rules explained plainly, 4 real list-
  building touchpoints wired to existing Day 1 review-request messaging, a 4-segment list
  structure, a monthly broadcast cadence (2-4 sends/month cap), 5 WhatsApp message templates, a
  full two-sided "Give a Dive, Get a Dive" referral program design (mechanics, terms, 3 message
  templates) that needs no CRM/software to run, and two tracking tables. Still blocked on
  `business-info.md` for the WhatsApp number, real trip/pricing data (needed to size the referral
  discount sensibly), and certifying-body affiliation. Nothing sent or executed — WhatsApp isn't
  a connected write channel here, and customer messaging always stays human-sent regardless per
  the hard rule.
- Next run: Day 14 (Corporate/group booking outreach list + pitch template) is next up — this is
  the last task under Phase 1-3 that isn't yet at least `[~]`. Once Day 14 is done, every Phase
  1-3 task will be drafted and waiting on `business-info.md` (and, for a few, on live site/CMS
  access and the Windsor account-cap fix) to become fully real; the routine will then have no new
  Phase 1-3 work to invent and will shift to updating this file to say so per the standing
  instructions, until business-info.md unblocks a real next step.

## 2026-09-23
- Repo was clean and in sync this time (`git status` clean, local `main` already matched
  `origin/main` at `861eaa5`, Day 13) — no repeat of the detached-HEAD/stale-branch hygiene issue
  logged on 2026-09-18/21/22.
- `business-info.md` still not present. Completed Day 14 (Corporate/group booking outreach list +
  pitch template) — see `day14-corporate-group-outreach.md`. Covers 5 prospect segments (corporate
  offsite/event planners, HR/L&D direct, college adventure clubs/fest committees, bachelor(ette)/
  wedding planners, CSR/team-building consultancies) with real prospect-finding methods per
  segment, a corporate-readiness checklist (GST invoicing, safety/cert one-pager, group capacity
  limit, PO-based billing) worth confirming before the first pitch goes out, 5 ready-to-send pitch
  templates, an outreach sequencing plan, and a tracking table. This was the segment Day 9
  deliberately deferred to today rather than duplicating. Still blocked on `business-info.md` for
  location, contact number, certifying body, group capacity, and group pricing tiers. Nothing sent
  — outreach always stays draft-only per the hard rule regardless of input completeness.
- Did not query Windsor today — this task doesn't touch GMB, Facebook, or any connected ad
  platform, so there was nothing to read or verify against live data.
- With Day 14 done, **every Phase 1-3 task is now at least `[~]` (drafted)** — none remain `[ ]`.
  Per the standing instructions, once every Phase 1-3 task is drafted/published, the routine
  should stop inventing new work and instead note here that everything is waiting on human review
  and on `business-info.md`. Next run: unless `business-info.md` has been added by then, expect the
  next session to do exactly that (confirm nothing new to draft, log it, stop) rather than starting
  on the "Ongoing (recurring)" section, since those items are themselves blocked on the same
  Windsor account-cap fix and aren't one-and-done deliverables to draft.

## 2026-09-24
- Repo was clean and already in sync with `origin/main` at `30a6bb1` (Day 14) — no detached-HEAD
  or stale-branch hygiene issue today.
- `business-info.md` still not present. All Phase 1-3 tasks remain `[~]` (drafted, none unblocked
  since yesterday) — same state as the 2026-09-23 run. Per the standing instructions, not
  inventing new work; the "Ongoing (recurring)" section stays out of scope since those items are
  one-and-done-not, and are themselves blocked on the same Windsor account-cap fix.
- Did not query Windsor today — nothing in scope for this run touches a connected platform, so
  there was nothing to read or verify.
- Next run: still waiting on `business-info.md` (biggest unlock) and, secondarily, the Windsor
  account-cap fix, live site/CMS access, and the Instagram/GSC connector additions listed under
  "Blocked on you" in TASKS.md. No action needed from the routine until one of those lands.

## 2026-09-25
- Repo hygiene: session started with local `HEAD` detached at `188c0c9` while the local `main`
  branch ref was stale at `30a6bb1` (Day 14) — the same recurring stale-branch pattern logged on
  2026-09-18/21/22. Checked out `main` and fast-forwarded it to `origin/main` (`188c0c9`) before
  starting — no data lost, no force-push needed.
- `business-info.md` still not present at the repo root. Every Phase 1-3 task in TASKS.md is
  already `[~]` (drafted) — none are `[ ]` — so per the standing instructions there is no new
  Phase 1-3 work to invent today, and the "Ongoing (recurring)" section stays out of scope since
  it's blocked on the same Windsor account-cap fix and isn't one-and-done deliverable work.
- Queried Windsor (`get_connectors`) to check whether the account owner has changed anything: the
  `google_my_business` account `locations/17253298120475111002` = "Deep Dive Trips" and
  `facebook_organic` account `1068114356395128` = "Deep Dive Trips" are both still connected as
  configured. Noted one new connector: `googleanalytics4` now lists a `www.ddtrips.in`-labeled
  account (`540396303`) that wasn't there before — GA4 for the client's own site is now connected
  in Windsor, which was one of the "Blocked on you" items. However, a live `get_data` pull against
  `google_my_business` (calls/website_clicks, Sept 1-24) still came back null/zeroed
  (`location_name: null, calls: null, website_clicks: 0`), so the Windsor Free-plan account-cap
  read-pause described in TASKS.md appears to still be in effect — the new GA4 connection doesn't
  yet mean real numbers are flowing. Did not touch Facebook or Instagram (no write action
  permitted there regardless).
- No GMB post published today: nothing in scope required a new GMB post, and publishing one
  without a fresh, real fact to post about (beyond what Day 1/Day 5 already drafted) would just be
  filler content, which isn't the goal.
- Next run: still waiting on `business-info.md` (biggest unlock — turns every Phase 1-3 draft into
  a publishable/sendable final version) and, secondarily, the Windsor account-cap fix (now half
  addressed via the new GA4 connector, but GMB/FB reads are still paused), live site/CMS access,
  and the Instagram/GSC-for-ddtrips.in connector additions listed under "Blocked on you" in
  TASKS.md. No action needed from the routine until one of those lands.

## 2026-09-26
- Repo hygiene: session started with local `HEAD` detached at `921ac44` while the local `main`
  branch ref was stale at `30a6bb1` (Day 14) — same recurring stale-branch pattern as prior runs.
  Checked out `main` and fast-forwarded it to `origin/main` (`921ac44`) before starting — no data
  lost, no force-push needed.
- `business-info.md` still not present at the repo root. Every Phase 1-3 task in TASKS.md is
  already `[~]` (drafted) — none are `[ ]` — so per the standing instructions there is no new
  Phase 1-3 work to invent today, and the "Ongoing (recurring)" section stays out of scope since
  it's blocked on the same Windsor account-cap fix and isn't one-and-done deliverable work.
- Queried Windsor (`get_connectors`) to check for account-owner changes: `google_my_business`
  location `locations/17253298120475111002` = "Deep Dive Trips" and `facebook_organic` account
  `1068114356395128` = "Deep Dive Trips" are both still connected as configured. No new
  connectors relevant to ddtrips.in since 2026-09-25 (GA4 `ddtrips.in` account `540396303` still
  present; Instagram for Deep Dive Trips and Google Search Console for ddtrips.in still not
  connected).
- Spot-checked `google_my_business` reads (calls/website_clicks/direction_requests, last 30d):
  still coming back null/zeroed (`location_name: null, calls: null, website_clicks: 0`) — the
  Windsor Free-plan account-cap read-pause described in TASKS.md is still in effect.
- No GMB post published today: nothing in scope required a new GMB post, and posting filler
  content with no new real fact behind it isn't the goal.
- Next run: still waiting on `business-info.md` (biggest unlock), the Windsor account-cap fix
  (GMB/FB reads still paused), live site/CMS access, and the Instagram/GSC-for-ddtrips.in
  connector additions listed under "Blocked on you" in TASKS.md. No action needed from the
  routine until one of those lands.
