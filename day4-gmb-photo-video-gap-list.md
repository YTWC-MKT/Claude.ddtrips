# Day 4 — GMB Photo/Video Gap List + Shot List to Request from Client (Deep Dive Trips)

**Note on method:** Windsor's read on the connected Google My Business location
(`locations/17253298120475111002`, Deep Dive Trips) is currently returning the plan-limit error
("reads are paused... Free plan includes 1 account, you have 14 connected") — same blocker
already flagged in TASKS.md under "Blocked on you." So this isn't an audit of the exact photo
count/categories live on the profile right now; it's the full gap-list-and-shot-list framework
built from Google's own gallery structure and what actually moves bookings for an adventure/dive
business, ready to run the moment either (a) someone disconnects unused Windsor accounts /
upgrades the plan so real media data comes through, or (b) whoever has GMB access just opens the
profile and checks off what's already there against this list.

Once real media data is available, the next pass can turn section 1 below into an exact "you have
X, you need Y more" count instead of a placeholder checklist.

---

## 1. Audit checklist — run this against the live profile (5 min)

Google Business Profile groups photos into categories. Check off what's actually populated,
note the current count, and anything under 3 photos in a category is a gap:

| Category | What goes here | Minimum to look credible | Current count (fill in) |
|---|---|---|---|
| Logo | Square logo, used as the profile icon everywhere | 1 | ☐ |
| Cover photo | The big banner image — should be the single best photo you have | 1 (kept current) | ☐ |
| Team | Instructors/guides, ideally in gear, ideally smiling/working not posed | 3+ | ☐ |
| At work ("Trips in action" for us) | Divers underwater, boat departures, briefings, surface intervals | 10+ | ☐ |
| Interior/Exterior | Shop front, office, gear storage, boat exterior | 3+ | ☐ |
| Additional | Everything else: gear close-ups, certifications on display, marine life shots, group photos | 10+ | ☐ |
| Videos | Any video content at all | 1+ (see section 3) | ☐ |

If any row is at 0 or 1, that's the priority gap — Google's own guidance and every local-SEO study
say listings with 100+ photos get dramatically more direction requests and website clicks than
listings with under 10, and for an activity where customers are deciding whether to trust
strangers with their safety underwater, photos are doing more selling than the description text
ever will.

## 2. Priority order if the client can only send a handful right now

Ask for these first, in this order — this is the "even 10 photos, make them these 10" list:

1. **A diver's-eye view mid-dive** — coral/wreck/marine life with a diver in frame for scale.
   This is the single highest-converting photo type for dive businesses; it answers "what will I
   actually see."
2. **A wide group/boat shot** — full boat, gear racked, people visibly having a good time. Signals
   group size, safety setup, professionalism.
3. **An instructor actively teaching** — briefing on the boat or in the pool, not posed. Builds
   trust that this is a real operation with real instruction, not a fly-by-night.
4. **A close-up of certified gear/tanks/regulators** — reassures on safety and maintenance
   standards.
5. **A customer's genuine reaction shot** — post-dive smile, high-five, thumbs up breaking the
   surface. Social proof without needing a written review.
6. **The team, in gear, group photo** — humanizes the business, matches "who am I trusting."
7. **Marine life close-up** (turtle, reef shark, manta, whatever is locally common) — this is what
   ranks in image search for "[location] diving" and gets saved/shared.
8. **Certification/logo wall or wallboard** — PADI/SSI affiliation, credentials visible.
9. **A short video clip (15-30 sec) of an actual dive or boat ride** — see section 3, videos
   dramatically outperform photos on engagement once posted.
10. **Before/after or "first-timer" shot** — someone clearly new to diving looking nervous-then-
    thrilled — this is the exact customer a lot of search traffic is looking to see themselves in.

## 3. Video guidelines (GMB technical specs, so nothing gets rejected)

- **Length:** 30 seconds to 30 minutes (short 15-30 sec clips perform best for GMB and can be
  reused as Reels — see Day 6 content calendar once that's built)
- **File size:** up to 100 MB
- **Resolution:** 720p minimum, landscape or square holds up better in the GMB gallery than
  vertical
- **What to actually film:** boat departure, descent, a few seconds of the dive itself, ascent/
  surfacing celebration — a single continuous "day in the life" clip beats a heavily edited one
  for authenticity
- At minimum, one video is enough to stop being at zero — anything is better than nothing here
  since so few competitors post video at all

## 4. Photo/video technical specs (so nothing gets rejected or looks bad)

- **Format:** JPG or PNG
- **Size:** between 10 KB and 5 MB per photo
- **Resolution:** minimum 250x250 px, but aim for 720px+ on the shortest side — phone camera
  photos from any device made in the last 5 years clear this easily
- **Avoid:** heavy filters/text overlays (GMB may reject or down-rank these), collages, and
  anything with visible watermarks from a phone editing app

## 5. The actual message to send the client (copy-paste ready)

This is the ask to send Deep Dive Trips' owner/team directly — plain language, no jargon, tells
them exactly what to send and how:

> Hi! To get the Google listing (and Instagram/Facebook) looking as good as the trips actually
> are, could you send over whatever you've got from recent trips? Doesn't need to be
> professional — phone photos/videos are perfect. Specifically, if you have them:
> 1. Photos of divers actually underwater (with fish/reef/wreck in frame)
> 2. A few shots of the boat, full of people, gear racked up
> 3. Any video clips from a dive — even 15-20 seconds of someone descending or surfacing
> 4. Photos of your instructors teaching/briefing
> 5. Customer reaction shots — post-dive smiles, high-fives, etc.
> 6. Anything with your PADI/SSI certification signage or wall visible
>
> Easiest way: just forward whatever's in your phone's camera roll or WhatsApp from the last few
> trips — I'll pick the best ones. If you have a Google Drive/Photos folder you already dump these
> in, send the link and I'll pull straight from there. The more the better; even the "not perfect"
> ones are useful for the gallery.

## 6. Handoff/organization convention (once assets start coming in)

- One shared folder (Drive), subfoldered by trip/date: `YYYY-MM-DD_Location_TripName/`
- Flag the client's top 3 favorites per trip in a `_picks` subfolder or by adding "PICK" to the
  filename — speeds up which ones get used first for GMB posts / socials
- Once this exists, add the folder link to `business-info.md` (see "Blocked on you" in TASKS.md)
  — that's what unlocks pulling real photos into GMB posts and the Day 6 content calendar instead
  of describing them generically

---
**Nothing above has been sent or published** — this is the framework + the ready-to-send request
message, for you to forward to the client (or use directly if you are the client). Once real
photos/videos start coming in via the message in section 5, future GMB posts (Day 5 onward) and
the Instagram/Facebook calendar (Day 6) can reference them directly instead of using placeholders.
