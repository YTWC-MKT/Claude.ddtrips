# Day 2 — Website Conversion Audit (ddtrips.in)

**Note on method:** Direct browser/fetch access to ddtrips.in is blocked from this automated
environment (network egress restriction), and CMS/URL-structure access hasn't been shared yet
(see "Blocked on you" in TASKS.md). So this isn't a page-by-page teardown of the live site —
it's an execution-ready audit checklist (run it against the live site in ~30-45 min) plus a
fully concrete, copy-paste-able tracking implementation plan that doesn't depend on seeing the
site first. Once someone runs the checklist below and notes what's actually on the site, send
the findings back and the next pass can get specific (exact CTA copy fixes, exact page
recommendations).

## 1. CTA placement audit — walk every page and score against this

For each of: Homepage, main trip/course listing page, individual trip/course detail pages,
About, Contact —

- [ ] **Above the fold on mobile**, is there one unmistakable action (Book Now / WhatsApp Us /
      Call Now)? If a visitor has to scroll to find how to contact you, that's the #1 leak for
      an adventure-travel site — most traffic here will be mobile, decision-in-under-60-seconds.
- [ ] Is the primary CTA **repeated** at: top nav/header (sticky if possible), end of hero,
      after each trip description, and in the footer? One CTA at the bottom of a long page is
      not enough.
- [ ] Is there a **single primary action per page** (not 4 competing buttons — "Book Now",
      "Learn More", "Contact Us", "Download Brochure" all at once dilutes clicks). Pick one
      primary (WhatsApp or Call, since diving trips are high-consideration/low-volume — people
      want to ask questions before paying) and make everything else secondary/text-link styled.
- [ ] Does every trip/course page CTA say **what happens next** — "WhatsApp us to check dates"
      reads better than a bare "Enquire" for a first-time visitor who doesn't know if this is a
      form, a call, or a chat.
- [ ] Is pricing (or "starting from ₹X") visible near the CTA, even on some pages? Hiding all
      pricing until enquiry adds friction and increases low-intent WhatsApp messages that waste
      time on both sides.
- [ ] Click-to-call (`tel:`) and click-to-WhatsApp (`wa.me` or `api.whatsapp.com`) links — are
      they real links (not an image of a phone number) so mobile users can tap straight through?
- [ ] Is there a visible **trust strip** near the CTA (Google rating + review count, PADI/SSI
      certification badges, "X divers trained", years in business) — adventure bookings are
      trust-gated purchases, proof needs to sit right next to the ask, not buried in an About page.
- [ ] Any **form** on the site (enquiry/contact form) — check: how many fields (should be ≤4:
      name, phone/WhatsApp, trip interested in, preferred dates — anything more kills
      completion), does it have a WhatsApp-first alternative next to it, does submission show a
      clear confirmation (not just a silent page reload)?

**Fix priority once audited:** missing/buried CTA on trip pages > too many competing CTAs on
homepage > no trust signals near CTA > form too long. Report back which of these actually apply
and the next update can turn this into an exact per-page punch list.

## 2. Mobile audit checklist

Most searches for "scuba diving [city/location]" and GMB profile clicks land on mobile. Check
on an actual phone (not just browser dev tools — dev tools miss real tap-target and font
rendering issues):

- [ ] Tap targets (buttons/links) are at least 44x44px with clear spacing — nothing requires a
      precise tap between two links
- [ ] No horizontal scrolling on any page
- [ ] Body text readable without pinch-zoom (16px minimum)
- [ ] Hero image/video doesn't push the CTA below the fold — if using a full-bleed hero image,
      cap its height on mobile so the CTA is visible without scrolling
- [ ] Forms use appropriate mobile keyboards (`type="tel"` for phone fields, `type="email"` for
      email) so the right keyboard pops up
- [ ] WhatsApp click actually opens the WhatsApp app (not a broken deep link) — test on both
      Android and iOS if possible, they can behave differently
- [ ] Menu/nav is a proper mobile hamburger or bottom bar, not a shrunk desktop nav
- [ ] Images are compressed/responsive (served at mobile-appropriate sizes, not full desktop
      resolution downscaled by CSS) — this is usually the single biggest mobile speed killer on
      photo-heavy travel sites

## 3. Page speed audit

Run these (free, no login needed) against the homepage and one trip detail page:
- **PageSpeed Insights**: https://pagespeed.web.dev/ — enter ddtrips.in, run both Mobile and
  Desktop, note the Core Web Vitals: LCP (target <2.5s), INP (target <200ms), CLS (target <0.1)
- **GTmetrix**: https://gtmetrix.com/ — gives a waterfall view showing exactly which images/
  scripts are slow

Common culprits on travel sites to check for specifically:
- [ ] Uncompressed/unresized hero and gallery images (single biggest fix, usually) — convert to
      WebP, resize to actual display dimensions, lazy-load anything below the fold
- [ ] Auto-playing background video on the hero (huge weight on mobile data — consider a static
      image + play button instead, or heavily compressed short loop)
- [ ] Third-party embeds (Instagram feed widgets, chat widgets, booking iframes) loaded
      synchronously and blocking render — defer/async them
- [ ] No browser caching / CDN headers set on static assets
- [ ] Web fonts blocking first paint — use `font-display: swap`

**Target:** mobile LCP under 2.5s. Every extra second of load time on mobile is a well-documented
conversion killer for local/travel intent searches — people bounce back to the GMB listing or a
competitor's result instead of waiting.

## 4. WhatsApp / call click-tracking plan (GA4 + Google Tag Manager)

This is the concrete, buildable spec — hand this directly to whoever has GTM/GA4 access for the
site (or if there's no GTM container yet, that's step 0 below).

### Step 0 — Prerequisites (if not already in place)
1. Create a Google Tag Manager container for ddtrips.in (tagmanager.google.com), get the GTM-XXXXXXX
   snippet installed in the site's `<head>`/`<body>` (most site builders — WordPress, Wix,
   Webflow — have a plugin/settings field for this, no code change needed beyond pasting the
   snippet).
2. Confirm a GA4 property exists for ddtrips.in and note its Measurement ID (G-XXXXXXXXXX). Link
   it inside GTM as a GA4 Configuration tag that fires on **All Pages**.

### Step 1 — Define the three conversion events
| Event name | Fires when | Why this name |
|---|---|---|
| `whatsapp_click` | Visitor clicks any link whose href contains `wa.me` or `api.whatsapp.com` | Matches GA4 naming convention (snake_case, verb-object) |
| `call_click` | Visitor clicks any link whose href starts with `tel:` | Same |
| `form_submit_enquiry` | Visitor successfully submits the enquiry/contact form | Distinguishes real enquiries from GA4's generic auto-tracked `form_submit` |

### Step 2 — GTM trigger setup (no code, point-and-click in GTM UI)
1. **Trigger: WhatsApp Click**
   - Trigger type: *Just Links* (or *All Elements* with Click URL)
   - Fire on: Click URL contains `wa.me` OR Click URL contains `api.whatsapp.com`
2. **Trigger: Call Click**
   - Trigger type: *Just Links*
   - Fire on: Click URL contains `tel:`
3. **Trigger: Enquiry Form Submit**
   - If the form is a simple HTML form: trigger type *Form Submission*, fire on the specific
     Form ID/Class of the enquiry form (get this from the site builder's form settings), with
     "Wait for tags" + "Check Validation" enabled so it only fires on a real successful submit.
   - If the form is a third-party embed (Typeform, Google Forms, a booking plugin): use that
     tool's own "thank you"/confirmation page or its native GTM trigger integration instead —
     link-click tracking won't catch embedded-iframe submissions.

### Step 3 — GA4 Event tags (one per trigger above)
For each: Tag type = *Google Analytics: GA4 Event*, Configuration Tag = the GA4 Config tag from
Step 0, Event Name = the event names from the table above, and add these event parameters:
- `page_location` = `{{Page URL}}` (built-in variable)
- `page_title` = `{{Page Title}}` (built-in variable)
- `link_url` = `{{Click URL}}` (for the WhatsApp/call tags — lets you see which specific button/
  page drove the click)

### Step 4 — Mark them as GA4 Conversions
In GA4 (Admin → Events), once the three events start reporting (test in GTM Preview mode first,
then publish), toggle **"Mark as conversion"** for `whatsapp_click`, `call_click`, and
`form_submit_enquiry`. This makes them available as conversion goals for any future Google Ads
campaigns (relevant for Phase 3, Day 12) and shows up in GA4's standard conversion reporting
without extra setup.

### Step 5 — Validate
- [ ] GTM Preview mode: click a WhatsApp link, a phone number, and submit the form on a test
      pass — confirm all three tags fire exactly once each, no duplicates
- [ ] GA4 DebugView: confirm the three events land with correct parameters
- [ ] Publish the GTM container
- [ ] Wait 24-48h, then check GA4 Reports → Engagement → Events to confirm real traffic is
      generating these events

### What this unlocks
Once live, this answers the question that currently has no answer: **which GMB posts, which
Instagram content, which trip pages actually drive a WhatsApp message or call** — not just
"traffic," but leads. It also feeds directly into the Day 3 task (GA4 conversion-event spec) and
becomes the source of truth for whether Phase 3 ad spend is working.

## 5. Immediate no-code-access wins to flag to whoever runs the site
These don't need GTM/dev access, just CMS/content edits, and are worth doing this week:
- [ ] Pin a WhatsApp click-to-chat button (floating or sticky) on every page if the site theme
      supports it — most WordPress/Wix themes have a free plugin for this (e.g. "WhatsApp Chat"
      plugin on WordPress) — single highest-leverage, lowest-effort fix for a diving business
      where most bookings start as a conversation, not a form
- [ ] Add the Google rating/review count near the top of the homepage if not already there
- [ ] Make sure the phone number in the footer/header is an actual `tel:` link, not plain text

---
**Status:** Draft audit checklist + tracking spec, not yet run against the live site or
implemented. Needs: (1) someone to walk the live site against the Section 1-3 checklists and
report back what's actually there, (2) GTM/GA4 access confirmed so Section 4 can be implemented.
Nothing here has been published or changed live — this is planning/spec output for your review.
