# Deep Dive Trips (ddtrips.in) — Client Acquisition Roadmap

Working file for the ongoing client-acquisition push. A scheduled cloud routine (Claude) runs
daily at ~9:00 AM IST, picks the next `[ ]` task, and produces a real deliverable — not just an
outline. Standing rule: **GMB posts get published automatically once they're built from real
facts (see business-info.md) with no placeholders left in them.** Facebook, Instagram, review
replies, ad spend, and anything sent to a customer (WhatsApp/email) always stay draft-only and
wait for a human yes — the routine will never touch those live.

Status legend: `[ ]` not started · `[~]` drafted, waiting on your approval or an input from you · `[x]` done · `[x]` (published) = actually live

## Blocked on you (can't route around these)
- [ ] Windsor.ai Free plan is capped at 1 connected account but has 14 — GA4/GMB/FB reads for
      ddtrips.in are returning zeroed placeholder data until you disconnect unused accounts or
      upgrade: https://onboard.windsor.ai/app/pricing
- [ ] Connect Instagram (Deep Dive Trips) inside Windsor — only Elegant Photo Studio and
      ShutterDeck are connected right now
- [ ] Connect Google Search Console for ddtrips.in inside Windsor — only elegantphotostudio.in
      is connected right now
- [ ] Share the live site URL structure / CMS access details if you want me to draft page-level
      SEO copy against the real pages instead of generic templates
- [ ] **Add `business-info.md` to this repo** with real specifics — upcoming trip
      names/dates/locations, prices you're OK showing, real photo/Drive links, WhatsApp number,
      cancellation policy, any real reviews you want quoted. Without this the routine can only
      produce placeholder drafts (`[Trip Name]`, `[Date]`) and nothing gets auto-published — this
      is the single biggest unlock for the automation.

## Phase 1 — Foundations
- [~] Day 1: GMB completeness checklist + review-request templates + first week of GMB posts (see today's output)
- [~] Day 2: Website conversion audit (CTA placement, mobile, page speed, WhatsApp/call click tracking plan) — see day2-website-conversion-audit.md. Note: direct site fetch is blocked from this environment, so it's a run-this-checklist audit + a fully concrete GA4/GTM tracking spec, not a live teardown.
- [~] Day 3: GA4 conversion-event spec (WhatsApp click / call click / enquiry form submit) to hand to whoever maintains the site — see day3-ga4-conversion-event-spec.md
- [~] Day 4: GMB photo/video gap list + shot list to request from the client — see day4-gmb-photo-video-gap-list.md
- [~] Day 5: Second week of GMB posts + Q&A seed questions — see day5-gmb-posts-week2-qa.md
      (placeholder draft only, still blocked on business-info.md for real specifics)

## Phase 2 — Content engine
- [~] Day 6: 2-week Instagram/Facebook content calendar (captions + shot list, reels-first) — see day6-instagram-facebook-content-calendar.md
      (placeholder draft only, still blocked on business-info.md for real specifics; IG/FB posts never auto-publish regardless)
- [~] Day 7: SEO landing-page copy draft for top 3 destination/course pages — see day7-seo-landing-page-copy.md
      (placeholder draft only, still blocked on business-info.md and site URL/CMS access)
- [~] Day 8: Local directory audit (TripAdvisor, JustDial, Sulekha, etc.) + NAP consistency list — see day8-local-directory-audit.md
      (framework + real submission links + tracking table; still blocked on business-info.md for the actual NAP values to fill in Step 0)
- [~] Day 9: Partnership outreach list (hotels/resorts/dive shops) + outreach email template — see day9-partnership-outreach.md
      (framework + real prospect-finding methods + 5 email templates + tracking table; still blocked on business-info.md for location/coast, contact number, and certifying-body affiliation)
- [~] Day 10: Blog/long-tail SEO topic list — see day10-blog-seo-topics.md
      (Ahrefs API returned "Insufficient plan" today, logged in STATUS.md; done manually per the
      task's own fallback note. 13 fully-briefed topics ready to draft now, 4 destination-specific
      topics blocked on business-info.md)

## Phase 3 — Paid + retention
- [~] Day 11: Meta ads campaign structure + creative brief (audiences, budgets, hooks) — see day11-meta-ads-campaign-brief.md
      (framework + real account structure/budget baseline/audience stack/4 creative concepts;
      still blocked on business-info.md for trip names/dates/prices/certifying body; ad spend
      always stays draft-only regardless per the hard rule)
- [~] Day 12: Google Ads keyword list + campaign structure (Search + Performance Max) — see day12-google-ads-keyword-campaign.md
      (framework + full Search account structure/keyword tiers/negatives/budgets/RSA copy for
      brand+trial-dive+certification ad groups + PMax sequencing plan; Ahrefs still plan-blocked
      so no real volume/CPC data, prioritized by intent instead; still blocked on business-info.md
      for coast/state, certifying body, prices, dates; ad spend always stays draft-only regardless)
- [ ] Day 13: WhatsApp broadcast list setup plan + referral program design
- [ ] Day 14: Corporate/group booking outreach list + pitch template

## Ongoing (recurring, not one-and-done)
- [ ] Weekly: review GMB insights (calls, website clicks, direction requests, search queries) once Windsor plan is fixed
- [ ] Weekly: respond to all new GMB/FB/IG reviews and comments
- [ ] Monthly: refresh ad creative, re-check keyword rankings
