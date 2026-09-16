# Day 7 — SEO Landing-Page Copy: Top 3 Destination/Course Pages (Deep Dive Trips)

**Note on method:** Two inputs this task needs are still outstanding — (a) `business-info.md`
(real trip names, dates, locations, prices, past reviews) and (b) the live site URL structure/CMS
access (both listed under "Blocked on you" in TASKS.md). Without either, page topics, URLs, and
every trip-specific fact below are bracketed placeholders. What's real and directly usable now:
the on-page SEO structure, the keyword targeting logic, the copy framework sentence-by-sentence,
the schema markup, and the internal-linking/CTA wiring back to Day 2's conversion audit and Day
3's GA4 events. Swap in real names/dates/prices and the actual URLs and this is postable as-is.

**Why these 3 page types:** without confirmed analytics (Ahrefs/GSC not yet connected — see
"Blocked on you"), I can't pull actual search volume for ddtrips.in's specific destinations. So
this draft covers the 3 page *archetypes* almost every Indian scuba-diving operator needs and
that reliably carry commercial search intent, based on how the category searches nationally:

1. **A flagship destination/trip page** — the highest-intent, highest-volume page type
   ("scuba diving in [destination]", "[destination] scuba diving price")
2. **A second destination/trip page** — same structure, different location, to capture
   destination-specific searches without cannibalizing page 1
3. **A certification/course page** — captures a different intent entirely (people researching
   "how to get scuba certified" rather than "book a dive trip"), typically has less competition
   and converts people earlier in their journey

Once real trip/course names exist, replace `[Destination A]`, `[Destination B]`, and
`[Certification Course]` throughout and confirm final URLs against the actual site map — do not
publish these as new pages without checking whether equivalent pages already exist on ddtrips.in
(duplicate/competing pages hurt rankings; the right move may be to rewrite an existing page in
place rather than create a new one).

---

## How to use this file

Each of the 3 sections below is copy-paste-ready for a page builder or CMS: title tag, meta
description, URL, H1, full body copy broken into the sections a diving-trip page needs, an FAQ
block (with schema notes), image alt-text guidance, and internal links. CTAs use the exact
tracked actions from `day3-ga4-conversion-event-spec.md` (`click_whatsapp`, `click_call`,
`form_submit_enquiry`) so analytics work the moment this copy goes live — see that file for the
click-handler/GTM trigger setup this assumes.

---

## Page 1 — Flagship Destination Page: `[Destination A]`

**Target keyword (primary):** scuba diving in [Destination A]
**Target keywords (secondary):** [Destination A] scuba diving price / [Destination A] diving
packages / scuba diving [Destination A] for beginners / best time to dive [Destination A]
**Search intent:** commercial — ready to compare operators and book
**Suggested URL:** `/scuba-diving-[destination-a-slug]/` (confirm against existing site
structure before publishing — do not create a duplicate of an existing trip page)

### Title tag (≤60 characters)
`Scuba Diving in [Destination A] | Deep Dive Trips`

### Meta description (≤155 characters)
`Book certified scuba diving trips in [Destination A] with Deep Dive Trips. [X] years experience,
small groups, all gear included. Check dates on WhatsApp →`

### H1
`Scuba Diving in [Destination A]`

### Body copy

**Intro (above the fold, 40-60 words):**
> [Destination A] is [1-2 sentence real description of the dive site — visibility, marine life,
> what makes it distinct, e.g. "known for its coral reefs and gentle currents, making it one of
> India's most beginner-friendly dive destinations"]. Deep Dive Trips runs [certified/PADI/SSI —
> confirm affiliation] guided dives here for both first-timers and certified divers, with small
> group sizes and all gear included.

**Primary CTA button directly under the intro** (per Day 2 audit — CTA must appear above the
fold, not just at page bottom): `[WhatsApp us to check dates →]` (tracked as `click_whatsapp`,
`cta_location: hero`)

**Section: What you'll dive**
> [2-3 real dive site names at this destination with 1 sentence each on depth range, typical
> marine life seen, and difficulty level — e.g. "[Site name]: 8-18m, gentle drift, frequently
> spots turtles and reef fish, suitable for Open Water divers and above."] Repeat for each site
> Deep Dive Trips actually runs at this destination.

**Section: Trips & pricing**
> Table or list, one row per trip type actually offered at this destination:
> | Trip | Duration | Who it's for | Price |
> |---|---|---|---|
> | [Discover Scuba Dive] | [half-day] | No experience needed | [₹X,XXX] |
> | [2-Tank Fun Dive] | [full day] | Certified divers | [₹X,XXX] |
> | [Certification Course] | [3-4 days] | First-time or upgrading divers | [₹XX,XXX] |
> If pricing isn't something the client wants public yet, replace the price column with
> `[Contact for pricing]` and route straight to WhatsApp — but a visible price band
> ("₹X,XXX–₹XX,XXX") reduces unqualified enquiries and is worth revisiting once comfortable (see
> Day 1 checklist, same recommendation for the GMB products list).

**Section: What's included**
> Bullet list of what's actually bundled — gear rental, boat transfer, guide/instructor,
> certification fee if applicable, refreshments. State clearly what's *not* included (hotel,
> meals off-boat, transport to the departure point) so there's no friction at checkout.

**Section: Safety & certification**
> [Real facts only: instructor certification body and level, dive insurance policy, safety
> equipment/briefing process, max group size, medical form requirement.] This section matters
> disproportionately for adventure-activity conversion — people need to trust the operator before
> they'll hand over a deposit, and this is the section most competitor pages skip.

**Section: Real trips, real divers** (social proof)
> [1-2 real customer quotes with first name + what they dived, pulled from actual reviews once
> available — do not fabricate quotes]. Photo grid of real trip photos with descriptive alt text
> (see Image alt-text below).

**Section: FAQ** (also markup as FAQPage schema — see below)
- **Do I need experience to dive at [Destination A]?** [Real answer — likely "No, our Discover
  Scuba Dive requires no certification, just basic swimming ability and a short briefing."]
- **What's the best time of year to dive here?** [Real seasonal answer]
- **What if I've never been in open water before?** [Real answer tying to the discovery dive]
- **Is there an age or health restriction?** [Real answer]
- **What's your cancellation/reschedule policy?** [Pull from Day 1's Q&A once business-info.md
  has it — keep this answer identical across every page and the GMB Q&A section for consistency]

**Closing CTA block** (repeat at bottom per Day 2 audit — long pages need a second CTA):
`[Check availability on WhatsApp →]` (`click_whatsapp`, `cta_location: footer`) and
`[Call us: [phone number] →]` (`click_call`, `cta_location: footer`)

### Image alt-text guidance
Descriptive, keyword-natural, never stuffed: `"Scuba diver exploring coral reef at [Destination
A dive site name]"`, `"Deep Dive Trips instructor briefing group before dive at [Destination
A]"`. Avoid generic `"IMG_2031.jpg"` alt text — this is free image-search SEO the site is
currently leaving on the table.

### Internal links
- Link to the `[Certification Course]` page (Page 3 below) wherever the copy mentions
  "certification" or "first time"
- Link to `[Destination B]` page under a "Also diving in India?" or footer "Other destinations"
  module
- Link to the homepage and to the GMB profile / Google review link near the social-proof section

---

## Page 2 — Second Destination Page: `[Destination B]`

Same structure as Page 1, built to avoid keyword cannibalization — every heading and meta
description below is deliberately phrased differently from Page 1 rather than swapping only the
place name, since search engines devalue near-duplicate pages.

**Target keyword (primary):** [Destination B] scuba diving trips
**Target keywords (secondary):** diving in [Destination B] India / [Destination B] diving cost /
[Destination B] snorkeling and diving
**Suggested URL:** `/scuba-diving-[destination-b-slug]/`

### Title tag
`[Destination B] Scuba Diving Trips | Deep Dive Trips`

### Meta description
`Explore [Destination B]'s dive sites with Deep Dive Trips — beginner to advanced, small groups,
certified instructors. Message us on WhatsApp for open dates →`

### H1
`Scuba Diving Trips in [Destination B]`

### Body copy sections
Use the identical section structure as Page 1 (What you'll dive / Trips & pricing / What's
included / Safety & certification / Real trips real divers / FAQ / closing CTAs), populated with
`[Destination B]`-specific facts once available. Do not copy Page 1's sentences verbatim even
with the place name swapped — write each section fresh around what's actually distinct about
this destination (different marine life, different trip length, different diver skill level
required) so the two pages read as genuinely different content to both users and search engines.

### FAQ (destination-specific — do not just repeat Page 1's FAQ)
- **How is diving at [Destination B] different from [Destination A]?** [Real comparative
  answer — this question captures people already considering Deep Dive Trips and deciding
  between destinations, high-intent traffic]
- **Can beginners dive at [Destination B]?** [Real answer]
- **How do I get to [Destination B] from [nearest major city/airport]?** [Real logistics —
  this is a common drop-off point if travel logistics aren't addressed on-page]
- **What's the cancellation/reschedule policy?** [Identical answer to Page 1, for consistency]

### Internal links
- Link back to `[Destination A]` page and to the `[Certification Course]` page
- Link to a travel-logistics or "how to reach us" page if one exists on the site

---

## Page 3 — Certification/Course Page: `[Certification Course]`

This page targets earlier-funnel, research-stage search intent ("how do I get scuba certified",
"scuba certification cost India") rather than "book a trip now" — different keyword set,
different competition, and it's often the page that ranks fastest since fewer local operators
build course-specific content instead of only destination pages.

**Target keyword (primary):** scuba diving certification course India
**Target keywords (secondary):** [PADI/SSI — confirm] open water certification cost / how to
become a certified diver / beginner scuba certification course
**Search intent:** informational → commercial (researching, close to ready to book)
**Suggested URL:** `/scuba-certification-course/`

### Title tag
`Scuba Diving Certification Course | Deep Dive Trips`

### Meta description
`Get certified with Deep Dive Trips — [X]-day [PADI/SSI] open water course, small batches, all
gear + certification fee included. WhatsApp us to check the next batch →`

### H1
`Scuba Diving Certification Course`

### Body copy

**Intro:**
> Want to dive anywhere in the world, not just on a guided trip? Our [Certification Course name,
> e.g. "PADI Open Water Diver"] course gets you internationally recognized certification in
> [X] days, no prior experience required.

**Primary CTA** directly under intro: `[WhatsApp us about the next batch →]` (`click_whatsapp`,
`cta_location: hero`)

**Section: What the course covers**
> Break into the real structure — e.g.:
> - **Day 1: Theory + confined water** — [real content: physics/physiology basics, equipment
>   familiarization, skills practice in a pool or shallow, calm water]
> - **Day 2-3: Open water dives** — [real content: number of open-water training dives required,
>   skills demonstrated, depth progression]
> - **Certification** — [real content: what card/certification is issued, how long it takes to
>   arrive, whether it's valid worldwide]

**Section: Who this is for**
> [Real eligibility: minimum age, swimming ability required, medical form/conditions to
> disclose, fitness level]. No prior diving experience needed — that's the point of the course.

**Section: What's included / course fee**
> [Real bullet list: instructor fee, gear rental for the course, certification/registration fee,
> course materials, number of open-water dives included.] Price: `[₹XX,XXX]` or
> `[Contact for pricing]`.

**Section: After certification**
> [Real content: what the certification unlocks — e.g. "Once certified, you can dive
> independently (with a buddy) at any dive site worldwide up to [X]m, and book our destination
> trips at the certified-diver rate rather than the discovery-dive rate."] — this paragraph is
> also the natural internal-link point to Page 1 and Page 2.

**Section: FAQ**
- **Do I need to know how to swim?** [Real answer]
- **How long does certification last / does it expire?** [Real answer]
- **What if I'm nervous about being underwater?** [Real answer — this objection is extremely
  common for first-time course bookers and worth answering directly and reassuringly]
- **Can I do the course in [X] days if I'm only visiting for a short trip?** [Real answer —
  addresses tourists on a fixed schedule]
- **What's the cancellation/reschedule policy?** [Identical answer to Pages 1 & 2]

**Closing CTA block:**
`[Check the next batch on WhatsApp →]` (`click_whatsapp`, `cta_location: footer`) and
`[Call us: [phone number] →]` (`click_call`, `cta_location: footer`) and, if an enquiry form
exists on this page per Day 3's spec, `[Enquire about this course →]` (`form_submit_enquiry`)

### Internal links
- Link to Page 1 and Page 2 from the "After certification" section
- Link to the GMB Q&A / reviews for social proof
- If a blog exists or is built later (Day 10), this page is the natural link target for any
  "is scuba diving safe" / "what to expect on your first dive" content

---

## Schema markup (all 3 pages)

Add **FAQPage structured data** for each page's FAQ block — this is what makes FAQ answers
eligible to show directly in Google search results (expanded search real estate, higher CTR with
no ranking-position change needed). Example structure for whoever implements this in the CMS:

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Do I need experience to dive at [Destination A]?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "[exact real answer text used on-page]"
      }
    }
  ]
}
```

For Pages 1 and 2, also consider **TouristTrip** schema (destination, duration) if the CMS/SEO
plugin supports it; for Page 3, **Course** schema (provider, course name, duration). Flag to
whoever maintains the site — this is a CMS-side implementation task, not something this routine
can push directly without site/CMS access.

## Cross-references
- CTA click tracking (`click_whatsapp`, `click_call`, `form_submit_enquiry`) → full GTM/GA4 setup
  in `day3-ga4-conversion-event-spec.md`
- CTA placement rules (above the fold + repeated at page bottom, mobile tap-target sizing) →
  `day2-website-conversion-audit.md`
- Once real photos exist per `day4-gmb-photo-video-gap-list.md`, use them here instead of stock —
  same images can be reused across the GMB profile, these landing pages, and the Day 6 social
  calendar for a consistent visual identity

---

**Nothing above is live anywhere** — this is copy for a human (or whoever has CMS access) to
review, drop in real specifics, confirm final URLs against the existing site map, and publish.
This routine cannot push website copy directly (no CMS/site access), so this task always ends in
a draft file regardless of the standing GMB auto-publish rule.
