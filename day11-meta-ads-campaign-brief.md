# Day 11 — Meta Ads Campaign Structure + Creative Brief (Deep Dive Trips)

Placeholder-marked draft. Ad spend/targeting always stays draft-only under the standing rule,
regardless of whether placeholders are filled — this file is a blueprint for a human to load into
Meta Ads Manager, not something this routine will ever execute. Every bracket below is a real
input still needed (mostly from `business-info.md`, which doesn't exist in this repo yet); nothing
here is invented pricing, dates, or trip names.

## 0. Before spending a rupee — prerequisites checklist

- [ ] Meta Pixel + Conversions API installed on ddtrips.in, firing on the three events from
      Day 3's spec (`whatsapp_click`, `call_click`, `enquiry_form_submit`) — ads without a pixel
      are flying blind and this is a 15-minute one-time setup for whoever holds site access
- [ ] Instagram (Deep Dive Trips) connected to the Facebook Page in Meta Business Suite, so ads
      can run as IG placements too, not just Facebook feed
- [ ] At least 3-5 real photos/videos per trip type ready (Day 4's shot list + Day 6's content
      calendar should be producing these already) — stock imagery under-performs badly for
      adventure travel, real customer footage is the single biggest lever on CTR
- [ ] `business-info.md` in this repo with: trip/course names, prices, next 4-6 weeks of
      confirmed dates, WhatsApp number, cancellation policy, any certifications (PADI/SSI) —
      every campaign below is structured around these slots

## 1. Account structure

```
Ad Account: Deep Dive Trips
└── Campaign 1: [BRAND] — Retargeting & Warm Audiences
│   └── Ad Set: Website visitors 30d (exclude converters)
│   └── Ad Set: IG/FB engagers 90d
│   └── Ad Set: WhatsApp click, no booking (from pixel event)
├── Campaign 2: [COLD] — Prospecting: Trial Dive / Fun Dive
│   └── Ad Set: Interest + lookalike stack (see §3)
├── Campaign 3: [COLD] — Prospecting: Certification Courses
│   └── Ad Set: Interest + lookalike stack (see §3)
└── Campaign 4: [SEASONAL] — Trip-specific / urgency (built fresh per upcoming batch)
    └── Ad Set: Retarget + narrow interest, tight date window
```

Objective for all four: **Conversions**, optimizing for the pixel event closest to revenue
(`enquiry_form_submit` or `whatsapp_click` — whichever has more volume once tracking has run for
2-3 weeks; start on `whatsapp_click` since that's the faster-firing proxy). Do not run a
Traffic or Engagement objective campaign for anything but the very first week while the pixel
learns — those optimize for clicks/likes, not people who actually book.

## 2. Budgets (starting point — real numbers, not placeholders, but explicitly a starting
   recommendation to revise after 2 weeks of real CPL data)

| Campaign | Daily budget | Rationale |
|---|---|---|
| 1 — Retargeting | ₹300/day | Small audience, cheap per-result, don't overspend chasing an audience that's already warm |
| 2 — Trial/Fun Dive prospecting | ₹500/day | Highest-volume, lowest-commitment offer — best top-of-funnel volume generator |
| 3 — Certification prospecting | ₹400/day | Higher intent, higher price point, naturally lower volume/higher CPL — that's fine |
| 4 — Seasonal/trip urgency | ₹300/day, only active [X] days before a specific trip date | Turn on 10-14 days out, off once the trip fills or departs |
| **Total baseline** | **₹1,200-1,500/day (~₹36,000-45,000/month)** | Adjust up only after Campaign 2's cost-per-WhatsApp-click is known and profitable against average booking value |

Minimum viable test budget if the above is too high to start: run only Campaign 2 at ₹500/day
for 2 weeks, get a real CPL number, then decide whether to add 1/3/4. **Do not skip straight to
all four campaigns on day one** — there's no CPL baseline yet to know if ₹1,200/day is even
sane for this business's margins, and that number belongs in `business-info.md` before scaling.

## 3. Audiences

**Lookalike sources to build the moment there's enough data (need 100+ events minimum, so this
may take 4-8 weeks post-pixel-install):**
- 1% LAL — WhatsApp click event
- 1% LAL — Instagram/Facebook engagers (once IG business account is connected to Windsor/Meta
  Business Suite — currently not connected per TASKS.md)
- 1% LAL — customer list uploaded from booking records, if [CRM/booking sheet] exists to export from

**Interest-stack audiences to run until lookalikes are viable (India-wide or geo-fenced to
[operating coast/state — still needed, flagged in Day 8/Day 9 too] + a 150km radius, since
divers travel for trips):**
- Core: Scuba diving, PADI, Open Water Diver, Snorkeling, Diving equipment
- Adjacent adventure: Trekking, Adventure travel, Backpacking, Bungee jumping, Skydiving —
  (adventure-activity cross-interest audiences convert well for dive trial offers even without
  diving-specific interest)
- Travel-intent: Recently traveled (India), International travel, [Nearest metro] to
  [operating location] travel searchers
- Age/gender: 20-45, all genders (do not narrow by gender — no data yet suggesting this business's
  customer base skews either way; test open, narrow later only if CPL data shows a clear split)
- Placements: Automatic (let Meta optimize Feed/Reels/Stories/Audience Network) — do not manually
  restrict placements this early, it only starves the algorithm of data

**Exclusions (apply to all cold campaigns):**
- Existing customers (once a customer list exists to exclude)
- Anyone who already converted on `enquiry_form_submit` in the last 90 days

## 4. Creative brief

**Format priority: video/Reels first.** Meta's own delivery data consistently favors native
vertical video for travel/adventure categories — a 15-25 second clip beats a static photo carousel
on cost-per-result almost every time in this category. Static images are the fallback only when
no usable video exists yet for a given trip.

### Ad concept 1 — "First-timer, no experience needed" (Campaign 2, Trial Dive)
- **Hook (first 2 seconds, must work with sound off):** on-screen text "You don't need to know
  how to swim well to try scuba diving" over underwater trial-dive footage
- **Body:** 3 quick cuts — nervous first step off the boat → underwater reaction shot (genuine
  smile/wide eyes, not staged) → surfacing high-five with instructor
- **Caption:** "Never dived before? Neither had [X]% of the people in this video a week ago.
  Trial dives at Deep Dive Trips include full gear, a certified instructor with you the whole
  time, and zero experience required. Next trial dive: [date]. Message us to grab a spot →"
- **CTA button:** Send WhatsApp Message
- **Needs from business-info.md:** real trial-dive stat/testimonial line, next available date,
  price if comfortable showing it (removes friction per Day 1's checklist logic)

### Ad concept 2 — "Get certified" (Campaign 3, Certification)
- **Hook:** "Get scuba certified in [X] days, dive anywhere in the world for life" over course
  montage (pool session → open water dives → certification card reveal)
- **Body:** What's included checklist as on-screen text (materials, dives, certification card,
  [PADI/SSI — confirm which] recognition)
- **Caption:** "A [PADI/SSI] Open Water certification with Deep Dive Trips means you can dive
  anywhere in the world, for life, with no expiry. Next course starts [date]. [X] spots left."
- **CTA button:** Learn More → links to the certification landing page from Day 7 once live
- **Needs:** certifying body confirmation, course dates/duration, price, landing page URL

### Ad concept 3 — "Social proof retargeting" (Campaign 1)
- **Format:** static image or short clip of a real 5-star review overlaid on a customer photo
  (with permission, per Day 1's review-reply/photo-request norm)
- **Caption:** "Don't just take our word for it — [quote from a real review]. Ready to book your
  own trip? [link/WhatsApp]"
- **CTA button:** Send WhatsApp Message
- **Needs:** at least 2-3 real reviews with permission to reuse the reviewer's name/photo

### Ad concept 4 — "Urgency/seasonal" (Campaign 4, built fresh per trip)
- **Hook:** "[X] spots left for [Trip Name] on [Date]"
- **Body:** location B-roll + price + what's included, 15 seconds max
- **Caption:** "[Trip Name] · [Date] · [Location]. [X] spots left. [Price if shown]. Book direct
  via WhatsApp, no booking fee →"
- **CTA button:** Send WhatsApp Message
- **Needs:** everything — this concept cannot be built at all until a specific upcoming trip
  exists in `business-info.md`; template is ready to fill the moment one does

## 5. Reporting cadence

Once campaigns are live, track weekly (folds into the existing "Weekly: review GMB insights" line
in TASKS.md's Ongoing section — add Meta Ads to that same weekly check once spend starts):
- Cost per WhatsApp click / cost per enquiry (the two pixel events from Day 3)
- CTR and thumb-stop rate by creative concept (kills the losers fast — adventure-travel ad fatigue
  sets in around 2-3 weeks per concept, plan to rotate creative on that cycle)
- Which audience (lookalike vs. interest-stack) is producing cheaper qualified leads, to
  reallocate budget toward it

## 6. What this routine will and won't do here

- **Won't:** call `execute_action` on any Meta/Facebook/Instagram connector for ads, ever — hard
  rule, not a judgment call. All of the above is a blueprint for a human to build in Ads Manager.
- **Won't:** invent a budget number pretending it's based on real margin data — the ₹1,200-1,500/
  day baseline above is a reasonable industry-standard starting test budget for this category and
  spend level, explicitly flagged as needing revision once real CPL exists, not a guess dressed up
  as a fact.
- **Next unlock:** `business-info.md` turns concepts 1-4 from templates into launch-ready ads in
  under an hour of copy work — this is the single highest-leverage file in the whole repo at this
  point, referenced by 8 of the 11 deliverables so far.
