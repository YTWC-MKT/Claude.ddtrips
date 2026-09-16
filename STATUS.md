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
