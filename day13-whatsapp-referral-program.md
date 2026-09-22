# Day 13 — WhatsApp Broadcast List Setup Plan + Referral Program Design (Deep Dive Trips)

Goal: turn every past customer into two things — a repeat booker and a free acquisition channel.
WhatsApp is the highest-open-rate channel available for an Indian adventure-travel business (people
already message on it to book; open rates on WhatsApp broadcasts routinely beat email 5-10x), and a
referral program converts the trust a happy diver already has with their friends into new leads at
close to zero cost per acquisition. Both pieces below are ready to run as soon as the one blocking
input — `business-info.md` — exists; nothing here has been sent to anyone or executed, per the
standing rule that all customer-facing messaging always stays human-sent.

**Hard rule reminder:** this entire task is customer messaging. Even once `business-info.md` lands
and every placeholder below is filled with real facts, this file still never gets auto-sent —
WhatsApp isn't a connected write channel in this setup at all, and even if it were, messaging always
stays draft-only per the standing rule. A human copies these templates and sends them.

---

## Part 1 — WhatsApp Broadcast List Setup Plan

### 1.0 Which WhatsApp tool to use

Two real options, pick based on volume and budget:

| Option | Best for | Cost | Key limitation |
|---|---|---|---|
| **WhatsApp Business App** (free, phone-based) | Under ~250 contacts, one person managing it | Free | Broadcast lists only reach contacts who have your number saved in their phone; no automation, no multi-agent access |
| **WhatsApp Business Platform (API)** via a BSP like Interakt, WATI, AiSensy, or Gupshup (all have India-focused pricing, ₹1,000-3,000/month starter tiers) | 250+ contacts, wants automation, tracking, multiple staff replying | ~₹1,000-3,000/mo + per-message cost for template messages outside the 24h window | Requires Meta business verification (few days), and every marketing message outside a live conversation must use a pre-approved template |

**Recommendation for Deep Dive Trips' likely current size:** start on the free Business App (it's
almost certainly what's in use already, based on the review-request templates already drafted in
Day 1). Move to an API-based tool once the list crosses ~200-250 real contacts or once broadcast
volume makes manual list management painful — that threshold is worth revisiting once real customer
counts exist (blocked on `business-info.md`).

### 1.1 Compliance — read this before sending anything (Meta can permanently ban a number for violating this)

- **Opt-in is mandatory.** Never add a number to a broadcast list just because it's in your phone —
  a customer has to actively agree to receive marketing messages from you. "Book a trip → add their
  number" is NOT itself opt-in; the number must confirm.
- **The 24-hour window rule:** you can freely reply to any message a customer sends within 24 hours
  of their last message (this covers most post-booking/post-trip conversation). Outside that window,
  only pre-approved **template messages** can be sent (Meta reviews and approves templates in
  advance) — this matters most for the API-based option; the free Business App effectively limits
  you to contacts who've messaged recently or who you message individually, since it has no
  broadcast-outside-window capability at all for cold sends.
- **Every broadcast needs a visible opt-out.** "Reply STOP to unsubscribe" or equivalent, honored
  immediately.
- **Never buy or scrape phone number lists.** Every number on the list must come from an actual
  Deep Dive Trips customer/lead interaction (booking form, GMB message, IG DM, in-person signup).

### 1.2 How to actually build the list (real acquisition points, not just "ask for numbers")

| Collection point | Method | Opt-in language to use at that point |
|---|---|---|
| At booking (whenever a customer books, in person, by call, or via WhatsApp) | Add one line to the booking confirmation flow | "Can I add you to our WhatsApp updates list? Occasional trip announcements and offers, unsubscribe anytime." |
| Post-trip (same moment as the Day 1 review-request message) | The review-request WhatsApp message itself doubles as an opt-in touchpoint since it's already a 1:1 message within the 24h window | Add one line to the existing Day 1 template: "Want first access to upcoming trip dates + occasional offers? Reply YES and we'll add you." |
| GMB / website / Instagram bio | A "click to WhatsApp" link (`wa.me/[number]?text=...`) with a pre-filled message like "Hi, I'd like to join the trip updates list" | Same — the click itself plus the pre-filled text is explicit opt-in |
| In-person at the dive site/shop | A printed card or sign-up sheet at checkout | "Scan to get trip dates + offers on WhatsApp" with a QR code to the same `wa.me` link |

### 1.3 Segmentation (build these as separate lists/labels from day one, even on the free app)

1. **Past customers — [Course/Certification] level** (e.g. completed Open Water) — most likely to
   upsell to the next certification level.
2. **Past customers — trial/fun dive only** — most likely to convert to a certification course with
   the right nudge.
3. **Enquired but didn't book** — highest-intent cold list; needs a different tone (re-engagement,
   not loyalty).
4. **Referral partners / repeat groups** (once Day 9's partnerships are live) — separate list, since
   their content should be partner-facing, not customer-facing.

(Exact past-customer counts and which certification levels Deep Dive Trips actually runs are blocked
on `business-info.md` — the segmentation logic above is ready to apply the moment real customer
records exist.)

### 1.4 Broadcast cadence and content mix

Target **no more than 2-4 messages per month per list** — WhatsApp is high-trust precisely because
it isn't over-used; treat every send as a withdrawal from that trust.

| Week | Content type | Goes to |
|---|---|---|
| 1 | Trip announcement / upcoming date | All active lists |
| 2 | (skip — no send) | — |
| 3 | Educational or behind-the-scenes (reuse GMB post content from Day 1/5, repurposed for WhatsApp) | All active lists |
| 4 | Offer / last-minute seats OR referral program reminder (alternate month to month) | Segmented by relevance |

### 1.5 Message templates

Every template below is placeholder-marked only where a real fact from `business-info.md` is
missing (trip names/dates, WhatsApp number, prices, certifying body). Nothing else is guessed.

---

**Template W1 — List opt-in confirmation (send immediately after someone opts in)**

> Welcome aboard! 🌊 You're on the Deep Dive Trips updates list — expect occasional trip dates,
> tips, and offers, never more than a few times a month. Reply STOP anytime to come off the list.
> Questions before your next dive? Just message us here.

---

**Template W2 — Trip announcement**

> New dates just opened: [Trip Name] at [Location] on [Date] 🐠 [1-2 lines on what makes this trip
> worth it — visibility, marine life, difficulty level]. [X] spots left. Reply here or tap to book:
> [booking link/WhatsApp number]

---

**Template W3 — Educational / behind-the-scenes (repurposed from GMB post cadence)**

> Ever wondered what actually happens during a [Open Water / trial dive — confirm which] course?
> Here's what your first day with us looks like: [3 short bullet points — pool/confined session,
> safety briefing, first open-water dive]. No experience needed, all gear included.

---

**Template W4 — Last-minute seat / urgency**

> Only [X] spots left for [Trip Name] on [Date] — if you've been thinking about it, this is the
> nudge 🌊 Reply here to lock your spot before we fill up.

---

**Template W5 — Off-season / re-engagement (for the "enquired but didn't book" list, sent after
60+ days of no activity)**

> Hey! It's been a while since we last spoke about diving with us — no pressure at all, just
> wanted to check if it's still on your radar. Happy to answer any questions (cost, what's
> involved, best time to go) whenever you're ready. 🤿

---

### 1.6 WhatsApp list tracking table

| List/segment | Platform (App/API) | Contact count | Last broadcast sent | Next scheduled send | Opt-outs this month | Notes |
|---|---|---|---|---|---|---|
| Past customers — certified | | | | | | |
| Past customers — trial/fun dive | | | | | | |
| Enquired, not booked | | | | | | |
| Referral partners | | | | | | |

---

## Part 2 — Referral Program Design

### 2.1 Why a referral program specifically (not just "ask happy customers to tell friends")

An unstructured ask ("if you know anyone, send them our way!") gets forgotten within a day. A
structured program with **a reward on both sides** — the referrer and the new customer — gives
people an actual reason to act *and* a concrete thing to send, which is what turns "I had a great
time" into an actual booking. Two-sided ("Give X, Get X") programs consistently outperform one-sided
ones because the referrer isn't asking a friend for a favor with nothing in it for them — they're
sharing a deal.

### 2.2 Recommended program structure

**"Give a Dive, Get a Dive" — two-sided discount referral**

| Party | Reward | When it's granted |
|---|---|---|
| Referrer (existing customer) | [₹X off / X% off] their next booking, OR a free [gear rental/upgrade — confirm which is cheapest for the business to give] | Once the referred friend completes (not just books) a paid trip |
| Referred friend (new customer) | [₹X off / X% off] their first booking | Applied automatically when they use the referrer's code at booking |

**Why "completes a trip" and not "books":** protects against no-shows/cancellations draining the
reward budget — the referrer reward only triggers once revenue is actually locked in.

### 2.3 Mechanics (no CRM needed — this works entirely on WhatsApp + a spreadsheet)

1. Every customer who completes a trip gets a **unique referral code** in their post-trip WhatsApp
   message (see Template R1 below) — simplest version: first name + last 3 digits of their phone
   number (e.g. `RAHUL482`), no software needed to generate it.
2. New bookers are asked "Were you referred by anyone? Enter their code for [X]% off" at the booking
   step (works whether booking is by WhatsApp, call, or a form — just needs to become a standard
   question asked at booking).
3. Whoever handles bookings logs each code used in a simple spreadsheet (columns below) and manually
   sends the referrer their reward confirmation once the referred friend's trip is completed.
4. No app, no auto-tracking, no cost beyond the discounts themselves — intentionally low-friction to
   launch immediately once `business-info.md` provides the actual discount economics that make sense
   against real trip pricing.

### 2.4 Terms (keep this short and send alongside the program, not buried in fine print)

- Referral reward applies only once the referred friend's trip is completed and paid in full.
- One reward per successful referral, no cap on total referrals per person.
- Referral discount cannot be combined with other active offers (confirm this is the policy Deep
  Dive Trips wants — some businesses do allow stacking to encourage bigger word-of-mouth pushes;
  flag this as a decision for the human to make once real margins are known).
- Rewards expire after [X months] if unused (standard practice — prevents an ever-growing unclaimed
  liability).

### 2.5 Message templates

---

**Template R1 — Referral code delivery (send as a follow-up to the Day 1 post-trip review-request
message, same 24h window, same message thread)**

> One more thing — if you had a great time, here's a way to say thanks that actually pays off: your
> referral code is **[CODE]**. Share it with a friend — they get [X]% off their first trip with us,
> and once they complete it, you get [₹X off / a free X] on your next dive. No limit on how many
> friends you refer 🌊

---

**Template R2 — Referral program reminder (broadcast, alternates with Template W4 in the monthly
cadence)**

> Quick reminder: your referral code **[CODE]** is still active — share it with anyone thinking
> about trying diving. They get [X]% off, you get [reward] once they book. Message us if you've
> lost track of your code and we'll resend it.

---

**Template R3 — Reward confirmation (sent once a referred friend completes their trip)**

> Good news — [Friend's Name] just completed their dive with us, referred by you! Your [₹X off /
> free X] is confirmed for your next booking, just mention this message when you book. Thanks for
> spreading the word 🙌

---

### 2.6 Referral tracking table

| Referral code | Referrer name | Date code issued | Referred friend name | Date friend booked | Friend's trip completed? (Y/N) | Referrer reward sent? (Y/N) | Reward given |
|---|---|---|---|---|---|---|---|
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |

### 2.7 What's still blocking a fully real (non-placeholder) version of this task

- `business-info.md` — need real trip/course pricing to set a referral discount and reward that
  actually make sense against margins (a flat ₹ discount vs. a % discount produces very different
  economics depending on average trip price, which isn't guessed here), the actual WhatsApp/booking
  number for the `wa.me` link, and the certifying-body affiliation referenced in Template W3.
- A decision from the business on which reward is cheaper to fulfill: a cash-equivalent discount vs.
  a free gear-rental/upgrade — this changes per-unit cost and is a real business decision, not
  something to assume.
- Whether Deep Dive Trips currently uses the free WhatsApp Business App or has any booking-software/
  CRM already in place — changes whether the manual-spreadsheet tracking above is the permanent
  method or a bridge until something better is set up.
- Did not query Windsor today — this task is WhatsApp/referral program design, which isn't a
  connected read/write platform in this setup; nothing to verify against live data.

Nothing above has been sent to anyone or executed — these are drafts for a human to review, adapt
once `business-info.md` exists, and load into whichever WhatsApp tool the business uses, per the
standing rule that all customer messaging always stays human-sent.
