# Day 3 — GA4 Conversion-Event Spec (ddtrips.in)

**Purpose of this doc:** hand this directly to whoever maintains the ddtrips.in site (developer,
agency, or site-builder admin). It's the implementation-ready spec for the three conversion
events flagged in the Day 2 audit — `whatsapp_click`, `call_click`, `form_submit_enquiry` — with
exact event schemas, two implementation paths (GTM point-and-click, or raw code if there's no GTM
access), the GA4 auto-tracking conflict to watch for, and a QA checklist to sign off before
calling it done. Day 2 covered *why* this matters and a summary of the approach; this is the
*build-it* version.

**Prerequisite note (unresolved as of this doc):** whether ddtrips.in already has a GTM container
and a GA4 property is one of the "Blocked on you" items in TASKS.md. Everything below works either
way — Method A assumes GTM exists (or gets installed as a 10-minute one-time step), Method B is
for a developer with direct code access and no GTM. Pick one method, not both, to avoid
double-firing.

---

## 1. Event inventory — exact schema

Use these names and parameters exactly. GA4 event names must be snake_case, ≤40 characters, and
these follow GA4's recommended-event parameter style so they show up cleanly in standard reports.

### Event 1: `whatsapp_click`

| Field | Value |
|---|---|
| Event name | `whatsapp_click` |
| Fires when | Visitor clicks any element whose resolved `href` contains `wa.me/` or `api.whatsapp.com` |
| Parameter: `link_url` | Full href of the clicked link (string) |
| Parameter: `link_text` | Visible text/aria-label of the clicked element (string) — lets you tell "WhatsApp Us" header button apart from a trip-page WhatsApp CTA |
| Parameter: `page_location` | `window.location.href` (string) |
| Parameter: `page_title` | `document.title` (string) |
| Parameter: `source_section` | One of: `header`, `hero`, `trip_page`, `sticky_button`, `footer`, `contact_page` — set manually per placement so you can see which CTA position actually converts (see Section 3) |

### Event 2: `call_click`

| Field | Value |
|---|---|
| Event name | `call_click` |
| Fires when | Visitor clicks any element whose resolved `href` starts with `tel:` |
| Parameters | Same five as `whatsapp_click` above (`link_url`, `link_text`, `page_location`, `page_title`, `source_section`) |

### Event 3: `form_submit_enquiry`

| Field | Value |
|---|---|
| Event name | `form_submit_enquiry` |
| Fires when | The enquiry/contact form successfully submits (not on click of the submit button — on confirmed submission, see Section 3 for the distinction) |
| Parameter: `page_location` | `window.location.href` |
| Parameter: `page_title` | `document.title` |
| Parameter: `form_id` | The form's HTML id/name, or a fixed string like `enquiry_form` if there's only one |
| Parameter: `trip_interest` | Value of the "which trip/course" field if the form has one, else omit |

**Why these three and not GA4's own auto-tracked events:** GA4's Enhanced Measurement
auto-tracks a generic `click` (outbound) and a generic `form_submit`, but those don't distinguish
a WhatsApp click from a random outbound link, or a real enquiry submission from someone submitting
a newsletter signup elsewhere on the page. Custom-named events are what let Google Ads (Phase 3,
Day 12) and GA4 reporting treat these specifically as business conversions instead of noise.

---

## 2. Conflict to resolve first: GA4 Enhanced Measurement double-counting

GA4 properties have **Enhanced Measurement** on by default, which auto-fires a generic `click`
event (marked `outbound: true`) for any link to an external domain — this includes `wa.me` and
`tel:` links if they're treated as outbound. Left as-is, you'd get both the generic auto-event and
the custom `whatsapp_click`/`call_click` event for the same click, inflating counts and confusing
reports.

**Fix — pick one:**
- **Recommended:** leave Enhanced Measurement's outbound-click tracking ON for everything else
  (it's useful for tracking clicks to Instagram/social links etc.), but make sure the custom
  events use distinct names (`whatsapp_click`, not `click`) so they appear as separate rows in GA4
  — don't try to suppress the generic one. Just make sure whoever reports on this later filters to
  the custom event names for the "real" conversion count, not the generic `click` event.
- **Alternative (cleaner data, more setup):** in GA4 Admin → Data Streams → your web stream →
  Enhanced Measurement settings, turn off "Outbound clicks" entirely and rely solely on the three
  custom events for all click-based conversion tracking. Do this only if no one on the team needs
  general outbound-click visibility (e.g. clicks to Instagram/TripAdvisor from the site).

Note this decision in the implementation ticket so it doesn't get re-litigated later.

---

## 3. Method A — Google Tag Manager (no code, point-and-click)

Use this if GTM is already installed, or is being installed as part of this work (10-minute
one-time setup: create container at tagmanager.google.com, paste the two-part snippet into the
site's `<head>` and right after `<body>`).

### 3.1 Variables to create first (Variables → New)
- **Built-in variables** (Variables → Configure → check these on): `Click URL`, `Click Text`,
  `Click Element`, `Page URL`, `Page Title`.
- **Custom JS Variable — `Source Section`**: since GA4 needs to know *where* on the page a
  WhatsApp/call link was clicked, add a `data-section` attribute to each CTA in the site's HTML/
  theme (e.g. `<a href="https://wa.me/91XXXXXXXXXX" data-section="hero">`), then create a GTM
  variable of type *Custom JavaScript* that reads `{{Click Element}}.getAttribute('data-section')`.
  If adding `data-section` attributes isn't feasible right now, skip this variable and hardcode
  `source_section` as `"unspecified"` in the tag — better to ship the other four parameters now
  than block on this one.

### 3.2 Triggers to create (Triggers → New)
1. **WhatsApp Click** — Trigger type: *Just Links*. Fire on: Some Link Clicks → `Click URL`
   contains `wa.me/` OR `Click URL` contains `api.whatsapp.com`.
2. **Call Click** — Trigger type: *Just Links*. Fire on: Some Link Clicks → `Click URL` starts
   with `tel:`.
3. **Enquiry Form Submit** —
   - If it's a plain HTML form on the page itself: Trigger type *Form Submission*, fire on the
     specific form (by ID/CSS selector from the site's form settings), with **"Wait for Tags"**
     and **"Check Validation"** both enabled so it only fires on a real, validated submit — not on
     every click of the submit button.
   - If it's a third-party embed (a booking plugin, Typeform, Google Forms iframe): standard GTM
     link-click/form-submit triggers won't see inside the iframe. Instead use the tool's own
     "thank you" / confirmation URL as a *Page View* trigger (Trigger type: Page View, fire on
     Page URL contains `/thank-you` or whatever the confirmation path is), or the tool's native
     GTM/webhook integration if it has one.

### 3.3 Tags to create (Tags → New), one per trigger
For each of the three: Tag type = **Google Analytics: GA4 Event**, Configuration Tag = the site's
existing GA4 Configuration tag (create one first if it doesn't exist yet, pointed at the GA4
Measurement ID `G-XXXXXXXXXX`), Event Name = the exact names from Section 1, Event Parameters =
the parameter list from Section 1 mapped to the GTM variables above (`{{Click URL}}` →
`link_url`, `{{Click Text}}` → `link_text`, `{{Page URL}}` → `page_location`, `{{Page Title}}` →
`page_title`, the custom JS variable → `source_section`; for the form tag, `form_id` and
`trip_interest` come from Data Layer Variables if the form pushes them, else hardcode `form_id`).

### 3.4 Mark as conversions
Once all three are firing correctly (see QA checklist below) and publishing: GA4 → Admin →
Events → toggle **"Mark as conversion"** for `whatsapp_click`, `call_click`, and
`form_submit_enquiry`. This is what makes them usable as Google Ads conversion goals later
(Phase 3, Day 12) without any further setup.

---

## 4. Method B — direct code (no GTM access)

If whoever maintains the site has code-level access but no GTM, this is the vanilla-JS
equivalent, using `gtag()` directly. Assumes the site already loads the global `gtag.js` snippet
(GA4's own base tag) somewhere in the `<head>` — if not, that has to go in first (standard
GA4 snippet, from GA4 Admin → Data Streams → Web → "View tag instructions").

Add this script once, site-wide (e.g. in a footer include or main JS bundle), after the gtag.js
snippet:

```html
<script>
(function () {
  function sourceSectionFor(el) {
    var withSection = el.closest('[data-section]');
    return withSection ? withSection.getAttribute('data-section') : 'unspecified';
  }

  document.addEventListener('click', function (e) {
    var link = e.target.closest('a[href]');
    if (!link) return;
    var href = link.getAttribute('href') || '';
    var isWhatsApp = href.indexOf('wa.me/') !== -1 || href.indexOf('api.whatsapp.com') !== -1;
    var isCall = href.indexOf('tel:') === 0;
    if (!isWhatsApp && !isCall) return;

    gtag('event', isWhatsApp ? 'whatsapp_click' : 'call_click', {
      link_url: href,
      link_text: (link.textContent || link.getAttribute('aria-label') || '').trim(),
      page_location: window.location.href,
      page_title: document.title,
      source_section: sourceSectionFor(link)
    });
  }, true);

  var enquiryForm = document.querySelector('#enquiry-form'); // replace selector with the real form's id
  if (enquiryForm) {
    enquiryForm.addEventListener('submit', function (e) {
      // Only fires this branch if the form's own validation/JS lets the submit proceed —
      // for a form that submits via fetch/AJAX, call this same gtag() call inside the
      // "success" callback instead of on the raw submit event, so failed submits aren't counted.
      var tripField = enquiryForm.querySelector('[name="trip_interest"]');
      gtag('event', 'form_submit_enquiry', {
        page_location: window.location.href,
        page_title: document.title,
        form_id: enquiryForm.id || 'enquiry_form',
        trip_interest: tripField ? tripField.value : undefined
      });
    });
  }
})();
</script>
```

Notes for the developer implementing this:
- Replace `#enquiry-form` with the real form's selector.
- If the form submits via AJAX/fetch (no full page reload), move the `gtag('event', 'form_submit_enquiry', ...)` call into the success callback of that request, not the raw `submit` listener — otherwise a failed/validation-blocked submission still gets counted.
- Add `data-section="hero"` / `data-section="header"` / `data-section="trip_page"` / `data-section="sticky_button"` / `data-section="footer"` attributes to a wrapping element around each WhatsApp/call CTA to populate `source_section` — same reasoning as the GTM method (Section 3.1). If skipped, `source_section` will just report `"unspecified"` for everything, which still works but loses the by-placement breakdown.
- If Enhanced Measurement's outbound-click auto-tracking is left on (see Section 2), this code will produce a second, separate `click` event alongside the custom one — expected, not a bug.

---

## 5. Custom dimensions (do this regardless of Method A or B)

`link_text`, `source_section`, and `trip_interest` are useful in ad-hoc Explore reports but won't
appear as filterable columns in standard GA4 reports until registered as custom dimensions:

GA4 → Admin → Custom definitions → Create custom dimension, for each of:
- `link_text` (event-scoped, event parameter: `link_text`)
- `source_section` (event-scoped, event parameter: `source_section`)
- `trip_interest` (event-scoped, event parameter: `trip_interest`)

(`link_url`, `page_location`, `page_title` don't need this — GA4 already has close built-in
equivalents in standard reports.)

---

## 6. QA checklist — sign off before calling this done

Run through this on a phone (not just desktop dev tools) before publishing/shipping to production:

- [ ] GTM Preview mode (Method A) or browser console with a `gtag` event listener/GA4 DebugView
      extension (Method B) is active
- [ ] Click a WhatsApp CTA in the header → confirm exactly one `whatsapp_click` event fires, with
      correct `link_url`, `link_text`, and `source_section: "header"`
- [ ] Click a WhatsApp CTA on a trip detail page → confirm `source_section: "trip_page"` (not
      `"header"` — catches copy-pasted trigger/attribute mistakes)
- [ ] Click a phone number link → confirm exactly one `call_click` event, correct `link_url`
      (should read `tel:+91XXXXXXXXXX`, not a display-formatted string)
- [ ] Submit the enquiry form with valid data → confirm exactly one `form_submit_enquiry` fires,
      `trip_interest` populated if that field exists
- [ ] Submit the enquiry form with invalid/incomplete data (trigger client-side validation) →
      confirm `form_submit_enquiry` does **not** fire
- [ ] Test on both Android Chrome and iOS Safari — WhatsApp deep links (`wa.me` vs
      `api.whatsapp.com`) can behave differently across the two and both need to register the click
      event regardless of whether the WhatsApp app actually opens
- [ ] GA4 DebugView (Admin → DebugView, or the GA4 Chrome extension) shows all three events
      landing with every parameter populated as expected, no duplicates beyond the expected
      Enhanced-Measurement generic `click` (Section 2)
- [ ] Publish the GTM container (Method A) or deploy the code (Method B)
- [ ] Wait 24–48h, then GA4 → Reports → Engagement → Events: confirm real traffic is generating
      all three events, then go do Section 3.4 (mark as conversions) if not already done

---

## 7. What this unlocks

Once live and validated, this is the data source for:
- **Weekly GMB insight review** (TASKS.md "Ongoing") — cross-referencing which GMB posts
  correlate with spikes in `whatsapp_click`/`call_click` on the days after they go up
- **Phase 2 content calendar** (Day 6) — which Instagram/Facebook posts actually drive site
  clicks vs. just likes
- **Phase 3 paid campaigns** (Day 11–12) — `whatsapp_click`, `call_click`, and
  `form_submit_enquiry` become the three conversion goals both Meta Ads and Google Ads campaigns
  optimize toward, instead of optimizing toward pageviews/traffic with no way to tell if it turned
  into a lead

---
**Status:** Full implementation-ready spec — not yet built or deployed. Needs: (1) confirmation of
whether GTM is already installed or needs the one-time setup, (2) the real GA4 Measurement ID
(`G-XXXXXXXXXX` placeholder above), (3) the real enquiry form's element ID/selector, (4) a
developer or site-builder admin to implement Method A or B and run the Section 6 QA pass. Nothing
in this document changes anything on the live site — it's a handoff spec.
