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
