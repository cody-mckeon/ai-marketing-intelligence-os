## GTM Audit: `book_now_offer_click`

### 1. Built-In Click Variables (Variables → Configure → Clicks)

All requested built-in click variables are **enabled**:

- Click Element
- Click Classes
- Click ID
- Click Target
- Click URL
- Click Text

---

### 2. Tag Search (Tags → workspace search)

Tags matching the search terms:

- `book_now_offer_click` → **GA4 - Special Offers - Book Now**
- `book now` → **GA4 - Special Offers - Book Now** (plus several non-GA4 “Book Now” tags)
- `offer click` → no results
- `GA4 Event` → unrelated results (converter/template tags)
- `booking` → no additional GA4 offer-click tag surfaced beyond the Book Now terms

---

### 3. Tag Details (most relevant tag)

- **Tag name:** GA4 - Special Offers - Book Now  
- **Tag type:** GA4 Event  
- **GA4 event name:** `book_now_offer_click`  
- **Measurement ID / configuration tag used:** `{{RW Las Vegas - GA4 - ID}}` (Google tag found in container; uses configuration of Google tag “RW Las Vegas - GA4”)  
- **Event parameters:**

| Parameter name | Value |
|---|---|
| event_category | {{RegEx - Offer Code}} |
| event_label | {{CJS - WsVars.GuestLoyalty}} |

**Not present** in this tag’s event parameters (observed): `page_location`, `page_title`, `offer_name`, `offer_category`, `cta_text`, `cta_type`, `link_url`, `destination_url`, `destination_domain`, `destination_vendor`, `rate_code`, `tower`

---

### 4. Trigger Details (trigger attached to the tag)

- **Trigger name:** Click - Special Offers - Book Now  
- **Trigger type:** Just Links (link click trigger with conditions)  
- **Trigger fires on:** Some link clicks (based on the conditions below)  
- **Trigger conditions:**
  - Click Text **starts with** `BOOK`
  - Click URL **contains** `rate=`

These conditions imply the trigger is trying to key off booking links that include a **rate code** (`rate=`).

---

### 5. Preview Mode Test (Tag Assistant)

**Tag Assistant preview could not be verified in this environment** (Preview mode / live Tag Assistant session did not successfully launch), so the following Tag Assistant-specific details are unknown from direct observation:

- Whether the Book Now GA4 tag fired in preview
- Which event triggered it
- Click URL / Click Text / Click Classes / Click ID values observed in Tag Assistant
- Page URL / Page Title values observed in Tag Assistant
- Whether rate code, tower, offer name, destination domain were visible in the Variables panel at runtime

**However, based on GTM configuration alone**, the tag should fire when:
- Click Text begins with `BOOK`
- Click URL contains `rate=`

So the tag is likely firing on booking links that include a rate parameter.

---

### 6. Final Assessment

- **Offer-level reporting:** **No**  
  The tag does not explicitly send `offer_name` or `offer_category` (and it doesn’t even send `link_url` / `destination_url`), so you can’t reliably attribute clicks to a specific offer in GA4 unless the offer name is derivable from `event_category` (Regex output) or `event_label` (CJS output), which is unlikely to be stable/clear.

- **CTA-level reporting:** **No**  
  The tag doesn’t send `cta_text` or `cta_type`. Trigger condition uses Click Text but that value is not passed into GA4 as a parameter.

- **Destination/vendor reporting:** **No**  
  The tag doesn’t send `destination_url`, `destination_domain`, or `destination_vendor`.

- **Booking engine URL visibility in GTM:** **Partial**  
  Trigger explicitly uses Click URL and checks `rate=`, so GTM can “see” the URL at trigger time, but **does not pass it to GA4** as an event parameter.

- **Rate code visibility:** **Partial**  
  Trigger checks `rate=`, but rate code is not passed into GA4 as `rate_code`.

- **Offer name visibility:** **Not in tag parameters**  
  Not sent as `offer_name`.

- **Missing metadata:**  
  `page_location`, `page_title`, `offer_name`, `offer_category`, `cta_text`, `cta_type`, `link_url`/`destination_url`, `destination_domain`, `destination_vendor`, `rate_code`, `tower`

- **What should be added to the tag:**  
  Add GA4 event parameters mapped from Click URL / Click Text / Page data / data layer, e.g.:
  - `cta_text` = {{Click Text}}
  - `cta_type` = `book_now`
  - `link_url` / `destination_url` = {{Click URL}}
  - `destination_domain` = {{Page Hostname}} of the click URL (or parse from Click URL)
  - `rate_code` = parse from Click URL (`rate=` parameter)
  - `offer_name` / `offer_category` = parse from page data layer or DOM (offer module context)
  - `tower` = parse if present (from URL or data layer)