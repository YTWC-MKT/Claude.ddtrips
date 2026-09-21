# Day 12 — Google Ads Keyword List + Campaign Structure (Search + Performance Max)

Placeholder-marked draft. Ad spend/targeting always stays draft-only under the standing rule,
regardless of whether placeholders are filled — this file is a blueprint for a human to load into
Google Ads, not something this routine will ever execute. Every bracket below is a real input
still needed (mostly from `business-info.md`, which doesn't exist in this repo yet, or from the
coast/state and certifying-body questions already flagged in Day 8/Day 9/Day 10); nothing here is
invented pricing, dates, trip names, or search-volume numbers.

**Data note:** Ahrefs (`subscription-info-limits-and-usage`) returned `{"error": "Insufficient
plan"}` again today — the API key isn't on a Keywords Explorer tier, same blocker as Day 10. No
real search-volume, CPC, or competition numbers were available, so none are invented below. Every
keyword is grouped by intent and priority instead of a fabricated volume figure. Once the Ahrefs
plan is fixed, run `keywords-explorer-overview` against the lists in §2 (country `in`) before
setting bids — that data should directly set the daily budget split in §3.

## 0. Before spending a rupee — prerequisites checklist

- [ ] Google Ads conversion actions linked to the same three GA4 events from Day 3's spec
      (`whatsapp_click`, `call_click`, `enquiry_form_submit`) via GA4 → Google Ads account
      linking, then imported as conversion actions — this is what both Search and Performance Max
      bid against, so it has to exist before either campaign type goes live
- [ ] Google Ads conversion linking confirmed working (send a real test event, check it shows up
      in Google Ads → Goals within 24h) before turning on any Smart Bidding strategy — Target
      CPA/Maximize Conversions with zero real conversion history just burns budget on noise
- [ ] Business Profile (the same GMB listing already connected in Windsor,
      `locations/17253298120475111002`) linked to the Google Ads account — this unlocks location
      assets, affects Performance Max's local inventory, and is a 2-minute one-time link
- [ ] At least 3-5 real photos/videos per trip type (Day 4's shot list + Day 6's content calendar)
      ready as Performance Max assets — PMax without real imagery falls back to weak
      auto-generated crops and underperforms badly for a visual category like diving
- [ ] `business-info.md` in this repo with: trip/course names, prices, next 4-6 weeks of confirmed
      dates, WhatsApp number, cancellation policy, certifying body (PADI/SSI — needed by Day 7,
      Day 9, and Day 10 too), and the coast/state Deep Dive Trips operates from (needed for every
      location-qualified keyword and geo-target below)

## 1. Account structure

```
Google Ads Account: Deep Dive Trips
├── Campaign 1: Search — Brand
│   └── Ad Group: Deep Dive Trips (exact + phrase brand terms)
├── Campaign 2: Search — Certification (high intent)
│   └── Ad Group: Open Water Certification
│   └── Ad Group: Advanced / Specialty Certification
├── Campaign 3: Search — Trial / Fun Dive (high intent)
│   └── Ad Group: Trial Dive — No Experience
│   └── Ad Group: Fun Dive — Certified Divers
├── Campaign 4: Search — Location + Generic Adventure (broader, lower intent)
│   └── Ad Group: [Coast/State] Scuba Diving
│   └── Ad Group: [Nearest Metro] Diving Trips / Weekend Diving
├── Campaign 5: Performance Max — Full-funnel
│   └── Asset Group: Trial Dive
│   └── Asset Group: Certification
│   └── Asset Group: Retargeting/Remarketing (warm audience signal)
```

**Why Search + PMax and not just one:** Search campaigns 1-4 give exact control over match type,
negatives, and ad copy for the keywords a diver actually types — worth keeping separate so budget
and reporting stay legible per intent tier. Performance Max fills in everything Search structurally
can't reach (Display remarketing, YouTube, Discover, Gmail, Maps) using the same GA4 conversion
events as the bidding signal, and is where real photo/video assets do the most work. Do not run
PMax alone from day one — without Search campaigns 1-3 running first to establish which keywords
and audiences actually convert, PMax has no signal to learn from and Google's own guidance is to
seed it with at least 2-4 weeks of Search conversion data first.

Bidding strategy for all Search campaigns at launch: **Maximize Clicks** with a manual max CPC cap
for the first 2-3 weeks (no conversion history yet to bid smart against) → switch to **Maximize
Conversions** once each campaign has ~15-30 real conversions logged → **Target CPA** only after
that, once a real CPA number exists to target. Performance Max always requires Smart Bidding
(Maximize Conversions or Target CPA) — launch it on Maximize Conversions with no CPA target set
until Search campaigns have produced enough conversion volume to set one sanely.

## 2. Keyword list by intent tier

No volume/CPC data available today (Ahrefs blocked) — priority order below is based on commercial
intent, not search volume. Re-rank once real numbers are pullable.

### Tier A — Branded (Campaign 1, own the SERP against anyone bidding on your name)
- `deep dive trips`
- `deep dive trips [coast/state]`
- `deep dive trips reviews`
- `ddtrips.in`
Match type: **Exact + Phrase** only. This ad group should have the lowest CPA in the whole
account — bid to always win position 1 on your own name.

### Tier B — Certification, high commercial intent (Campaign 2)
Ad Group: Open Water Certification
- `scuba diving certification [coast/state]`
- `[PADI/SSI — confirm which] open water course [coast/state]`
- `learn scuba diving [coast/state]`
- `open water diver course india`
- `scuba diving course near me` (needs location extensions/geo-targeting to be relevant — see §5)
- `get scuba certified india`

Ad Group: Advanced / Specialty Certification
- `advanced open water diver [coast/state]`
- `scuba diving specialty courses india`
- `[PADI/SSI] advanced certification [coast/state]`
- `deep diver certification india`

Match type: **Phrase + Exact** for the specific-course terms, one broad-match ad group with a
tight budget cap as a controlled experiment (broad match needs the conversion data from §0 to be
safe — don't run it before conversion tracking is verified).

### Tier C — Trial/fun dive, high commercial intent, lower price point (Campaign 3)
Ad Group: Trial Dive — No Experience
- `trial scuba dive [coast/state]`
- `try scuba diving [coast/state]`
- `scuba diving for beginners india`
- `first time scuba diving [coast/state]`
- `discover scuba diving india`
- `scuba diving no experience needed`

Ad Group: Fun Dive — Certified Divers
- `fun dive [coast/state]`
- `certified diver trip [coast/state]`
- `scuba diving trip for certified divers india`

Match type: **Phrase + Exact**. This is the highest-volume, lowest-friction offer (mirrors Day
11's Meta Campaign 2 logic) — expect this ad group to drive the most clicks in the account.

### Tier D — Location + generic adventure, broader funnel (Campaign 4)
Ad Group: [Coast/State] Scuba Diving
- `scuba diving [coast/state]`
- `diving spots [coast/state]`
- `best scuba diving in india`
- `scuba diving packages [coast/state]`
- `water sports [coast/state]`

Ad Group: [Nearest Metro] Diving Trips / Weekend Diving
- `weekend diving trip from [nearest metro]`
- `scuba diving trip from [nearest metro]`
- `adventure trip [coast/state] from [nearest metro]`

Match type: **Phrase**, tighter budget cap than Tiers B/C — this tier casts wider and will have a
higher cost-per-conversion, its job is top-of-funnel volume and remarketing-list building for
Performance Max, not direct ROAS.

### Negative keywords (apply at account level, all Search campaigns)
Block low-intent, wrong-intent, and free/job-seeker traffic:
- `free`, `job`, `jobs`, `career`, `salary`, `internship`, `hiring`, `vacancy`
- `course fees` is fine to keep (commercial), but `fees waiver`, `scholarship` should be excluded
- `movie`, `documentary`, `wallpaper`, `game`, `simulator`
- `shark diving` / `cage diving` — exclude unless this is actually offered (confirm in
  `business-info.md`; if it is offered, move these into Tier D instead of excluding)
- `equipment for sale`, `buy scuba gear`, `scuba gear price` — retail-intent, not trip-intent,
  unless Deep Dive Trips also sells gear (confirm)
- `course syllabus pdf`, `how to become a dive instructor` — instructor-training and
  research-only intent, different funnel than a paying trip customer
- Competitor brand names — **do not add as negatives by default**; whether to actively bid on a
  named competitor's brand terms in a separate campaign is a judgment call for the human running
  the account (some categories tolerate it, some invite retaliation) — flagged here as a decision
  point, not made for you

## 3. Budgets (starting point — real numbers, not placeholders, explicitly a starting
   recommendation to revise once real CPC/conversion data exists)

| Campaign | Daily budget | Rationale |
|---|---|---|
| 1 — Brand | ₹150/day | Should rarely spend the full budget — brand CPCs are cheap, cap exists mainly to prevent a bidding-war edge case |
| 2 — Certification | ₹500/day | Highest price-point offer, worth paying more per click for; naturally lower click volume |
| 3 — Trial/Fun Dive | ₹600/day | Highest-volume, lowest-friction offer — best top-of-funnel conversion generator, mirrors Day 11's Meta Campaign 2 logic |
| 4 — Location/Generic | ₹350/day | Broader intent, higher expected cost-per-conversion, budget capped so it doesn't crowd out Tiers B/C |
| 5 — Performance Max | ₹400/day, **do not launch until Campaigns 2-4 have 2-4 weeks of conversion data** | Needs a real bidding signal to learn from; launching PMax with zero conversion history wastes the learning-phase budget |
| **Search total at launch (Campaigns 1-4)** | **₹1,600/day (~₹48,000/month)** | Launch Search first |
| **Full account once PMax turns on** | **₹2,000/day (~₹60,000/month)** | Add PMax only after the Search learning phase above |

Minimum viable test budget if the above is too high to start: run only Campaign 3 (Trial/Fun Dive)
at ₹500/day for 2-3 weeks to get a real CPA number, same sequencing logic as Day 11's Meta
recommendation — **do not launch all five campaigns on day one.** There's no CPA baseline yet to
know whether ₹2,000/day is sane for this business's margins, and that number belongs in
`business-info.md` (or a real CPA readout after a few weeks) before scaling.

This is a similarly-sized budget to Day 11's Meta recommendation (₹1,200-1,500/day) — expect Search
intent-keyword traffic to convert at a meaningfully higher rate than Meta's interest-based cold
prospecting, so a slightly higher Google Ads budget per rupee spent is reasonable once both are
running and comparable CPA data exists to actually check that assumption.

## 4. Ad copy (Responsive Search Ads — provide the max Google allows: 15 headlines, 4 descriptions
   per ad group; below are the ones ready to write now, rest is templated pending business-info.md)

### Ad Group: Trial Dive — No Experience (Campaign 3)
**Headlines (30 char max each):**
- Trial Scuba Dive, No Experience
- Try Diving in [Coast/State]
- Certified Instructor With You
- Full Gear Included
- Next Trial Dive: [Date]
- Book via WhatsApp — No Fee
- Deep Dive Trips — [Coast/State]
- [X]% Say It's Easier Than Expected *(needs a real stat/testimonial)*

**Descriptions (90 char max each):**
- Never dived before? Full gear, certified instructor, zero experience required. Book today.
- Trial dives from [Price]. Message us on WhatsApp for the next available date.

**Final URL:** Day 7's certification/trial-dive landing page once live · **CTA:** Call or
WhatsApp click (matches the Day 3 conversion events this campaign bids against)

### Ad Group: Open Water Certification (Campaign 2)
**Headlines:**
- Get Scuba Certified in [X] Days
- [PADI/SSI] Open Water Course
- Dive Anywhere, For Life
- Certification Never Expires
- Next Course Starts [Date]
- [X] Spots Left This Batch
- Deep Dive Trips — [Coast/State]

**Descriptions:**
- [PADI/SSI] Open Water certification with Deep Dive Trips. Dive anywhere in the world, for life.
- Includes materials, pool + open water dives, certification card. Next batch: [Date].

**Final URL:** Day 7's certification landing page once live · **CTA:** Enquiry form / WhatsApp

### Ad Group: Deep Dive Trips (Campaign 1, Brand)
**Headlines:**
- Deep Dive Trips — Official Site
- Scuba Diving in [Coast/State]
- Trial Dives & Certification
- Book Direct, No Booking Fee
- Read Real Customer Reviews

**Descriptions:**
- The official Deep Dive Trips site. Trial dives, certification courses, and dive trips.
- Book direct via WhatsApp — real reviews, real instructors, no third-party markup.

**Sitelink assets (all campaigns):** Trial Dives | Certification Courses | Reviews | Contact/
WhatsApp — link each to the matching Day 7 landing page once live, else to the homepage as a
placeholder.

**Callout assets:** Certified Instructors · Full Gear Included · [PADI/SSI] Affiliated · Book via
WhatsApp — No Fee (drop any callout whose fact isn't confirmed in `business-info.md` yet rather
than publishing an unverified claim).

Ad Groups for Tier B's Advanced/Specialty, Tier C's Fun Dive, and all of Tier D are structurally
identical to the two written out above — same pattern (need/benefit headline, date/urgency
headline, brand headline, two benefit-led descriptions) — write those the moment
`business-info.md` exists, same hour of copy work Day 11 flagged for the Meta creative concepts.

## 5. Location targeting

Needs the same input already flagged in Day 8 (NAP audit) and Day 9 (partnership outreach): which
coast/state Deep Dive Trips operates from. Once known:
- **Primary geo-target:** the operating coast/state itself, radius targeting around the actual dive
  site/base of operations (divers travel locally to reach a coastline)
- **Secondary geo-target:** top 3-5 source metros for India's dive-tourism traffic (a real list
  needs a GA4 geography pull once the Windsor account-cap issue clears — Day 3's spec already
  wires this event data up, it just isn't readable yet)
- **Exclude:** locations outside India unless the business wants to test outbound/diaspora
  interest — start India-only, expand only with evidence

## 6. What this routine will and won't do here

- **Won't:** call `execute_action` on any Google Ads connector — Windsor's write-action coverage
  doesn't currently list `google_ads` as connected for this account anyway (only
  `google_my_business` and `facebook_organic` are connected per today's `get_connectors` check),
  and ad spend/targeting stays draft-only under the hard rule regardless.
- **Won't:** invent search volume, CPC, or competition numbers to make this file look more
  data-backed than it is — Ahrefs is plan-blocked (`Insufficient plan`, same as Day 10), so every
  keyword below is prioritized by intent logic, not fabricated metrics.
- **Next unlock:** `business-info.md` turns the ad copy templates in §4 into launch-ready RSAs in
  under an hour, same as Day 11's Meta concepts — this remains the single highest-leverage file in
  the repo, now referenced by 9 of the 12 deliverables so far. Separately, fixing the Ahrefs plan
  (or the Windsor 14-accounts-on-Free-plan cap, a different blocker on a different platform) would
  let a future run replace §2's intent-only ranking with real volume/CPC-prioritized keyword bids.
