# Tracking Health Audit

Status: Partially ready with attribution caveat

## Source Inputs

* Campaign brief: `inputs/campaign-brief/summer-offers-campaign-brief.md`
* GA4 landing page export notes: `inputs/manual-notes/ga4_landing-page-first-read_notes.md`
* GA4 source / medium export notes: `inputs/manual-notes/ga4_landing-page-by-source-medium_first-read_notes.md`
* GA4 events export notes: `inputs/manual-notes/ga4_events_first-read_notes.md`
* Summer Offers page tracking audit note: `inputs/manual-notes/summer-offers-page-tracking-audit.md`
* Book Now / booking engine attribution notes: `inputs/manual-notes/book-now-booking-engine-attribution-finding.md`

## Readiness Status

### Ready

* Directional Summer Offers page traffic reporting
* Source / medium reporting with caveats
* Basic event-volume reporting
* Offer-level Book Now click reporting
* Offer-category Book Now click reporting
* Rate-code handoff reporting
* Destination/vendor reporting for Book Now CTAs
* Booking-engine `view_item` reporting by Summer Offers rate code

### Partially Ready

* Booking-engine funnel reporting

GA4 confirms that `reservations.rwlasvegas.com` sends booking-engine activity into the RW Las Vegas GA4 property, including `view_item` and `begin_checkout`. However, Summer Offers rate-code context appears to be visible at the booking-engine shop/view stage but not in checkout page locations.

### Not Ready

* Confirmed offer-level checkout attribution
* Confirmed offer-level hotel purchase attribution
* Confirmed offer-level hotel revenue attribution
* Final leadership revenue reporting by Summer Offer

## Key Findings

The Summer Offers page includes trackable offer metadata, including offer name, offer category, CTA text, destination domain, vendor type, rate code, and tower.

The `book_now_offer_click` event has been enhanced and validated in GTM and GA4. It now captures standardized metadata needed for offer-level and booking-handoff reporting.

Validated Book Now metadata includes:

* `offer_name`
* `offer_category`
* `rate_code`
* `destination_vendor`
* `cta_type`
* `component_name`
* `cta_text`
* `link_url`
* `destination_url`
* `destination_domain`
* `tower`

GA4 custom dimensions were created or confirmed for the key reporting fields needed in the first release:

* Offer Name
* Offer Category
* Rate Code
* Destination Vendor
* CTA Type
* Component Name

The booking engine subdomain, `reservations.rwlasvegas.com`, is present in GA4 Explore and sends booking-engine activity into the RW Las Vegas GA4 property.

Confirmed booking-engine events include:

| Event            | Hostname                      | Status    |
| ---------------- | ----------------------------- | --------- |
| `page_view`      | `reservations.rwlasvegas.com` | Confirmed |
| `session_start`  | `reservations.rwlasvegas.com` | Confirmed |
| `first_visit`    | `reservations.rwlasvegas.com` | Confirmed |
| `view_item`      | `reservations.rwlasvegas.com` | Confirmed |
| `begin_checkout` | `reservations.rwlasvegas.com` | Confirmed |

Summer Offers rate codes are visible on booking-engine shop URLs and `view_item` activity.

Example booking-engine shop URL:

```text
https://reservations.rwlasvegas.com/ibe/shop.aspx?propertyid=17726&rate=DSMCD26&selectedTower=CONRAD&selectedRate=DSMCD26
```

However, booking-engine checkout URLs do not appear to preserve the Summer Offers rate-code context.

Example checkout URLs:

```text
https://reservations.rwlasvegas.com/ibe/combocheckout.aspx?hotelID=17726&lang=en-us&hgID=0&currID=1
```

```text
https://reservations.rwlasvegas.com/ibe/cart.aspx?hotelID=17726&lang=en-us&currID=1
```

These checkout URLs do not include:

* `rate`
* `selectedRate`
* `selectedTower`

As a result, GA4 can currently confirm booking-engine checkout activity generally, but cannot confirm offer-level checkout attribution by Summer Offers rate code from page location alone.

Hotel booking-engine `purchase` events were not confirmed in the reviewed Explore data. Purchase events visible in the checkout/purchase review appeared to be associated with `tix.axs.com`, not hotel booking-engine purchases.

## Confirmed GTM Findings: Book Now Offer Click

* GTM tag name: `GA4 - Special Offers - Book Now`
* Tag type: GA4 Event
* GA4 event name: `book_now_offer_click`
* Trigger name: `Click - Special Offers - Book Now`
* Trigger type: Just Links
* Trigger condition: Click Text starts with `BOOK`
* Trigger condition: Click URL contains `rate=`

The enhanced tag now passes standardized event parameters for offer, CTA, destination, rate-code, and booking-handoff reporting.

Current standardized event parameters include:

| Parameter            | Purpose                                       |
| -------------------- | --------------------------------------------- |
| `offer_name`         | Identifies the clicked offer                  |
| `offer_category`     | Groups offer by category                      |
| `rate_code`          | Captures booking-engine rate code             |
| `destination_vendor` | Identifies handoff destination/vendor         |
| `cta_type`           | Standardizes CTA action type                  |
| `component_name`     | Identifies broad promotional module type      |
| `cta_text`           | Captures visible CTA text                     |
| `link_url`           | Captures clicked URL                          |
| `destination_url`    | Captures destination URL                      |
| `destination_domain` | Captures destination hostname                 |
| `tower`              | Captures selected hotel tower where available |

## Validated Summer Offers Rate Code Mapping

| Rate Code | Offer Name                | Offer Category | Tower  |
| --------- | ------------------------- | -------------- | ------ |
| `DSMCD26` | The Conrad Complete       | hotel          | CONRAD |
| `DCP26`   | Conrad Pool Package       | hotel          | CONRAD |
| `DSPCC26` | Warm Days & Bold Flavors  | dining         | CONRAD |
| `DSPHH26` | Famous Foods Street Feast | dining         | HILTON |
| `DSMHH26` | Hilton Summer Escape      | hotel          | HILTON |

## Directional Reporting Guidance

Current GA4 traffic and event data can be used directionally to understand page traffic, source / medium mix, and broad event-volume signals.

The enhanced `book_now_offer_click` event can now support more reliable reporting for:

* Offer-level Book Now clicks
* Offer-category Book Now clicks
* CTA type
* Destination/vendor handoff
* Rate-code handoff
* Tower where available

Booking-engine `view_item` data can support directional rate-code view reporting because Summer Offers rate codes are visible on booking-engine shop URLs.

Do not use GA4 revenue or purchase data as final leadership revenue attribution until purchase definitions, booking-engine purchase tracking, and rate-code persistence through checkout/purchase are validated.

## Metadata Gaps Limiting Reporting

* Offer-level checkout reporting is limited because Summer Offers rate code does not appear in booking-engine checkout page locations.
* Offer-level hotel purchase reporting is not confirmed.
* Offer-level hotel revenue attribution is not confirmed.
* Booking-engine item-level metadata could not be fully validated in GA4 Explore due to item/event dimension compatibility limitations.
* File-download reporting still needs review to confirm whether PDFs include file metadata and related offer attribution.
* Other CTA events, including Reserve, Buy Tickets, Learn More, Check Rates, and file downloads, still need the same metadata audit.

## Reporting Implication

Safe to report:

* Summer Offers traffic
* Source / medium mix with UTM caveats
* Offer-level Book Now clicks
* Offer-category Book Now clicks
* Rate-code handoffs to the booking engine
* Destination/vendor handoffs
* Booking-engine `view_item` activity by Summer Offers rate code

Do not yet report as confirmed:

* Offer-level checkout starts
* Offer-level hotel purchases
* Offer-level hotel revenue
* Full Summer Offers revenue attribution

## Recommended Fixes

### Completed / Implemented

* Enhanced the existing `book_now_offer_click` GA4 event.
* Added standardized offer, CTA, destination, vendor, and rate-code parameters.
* Registered or confirmed key GA4 event-scoped custom dimensions.
* Validated the event in GTM Preview.
* Validated live event visibility in GA4 DebugView / Realtime.
* Confirmed booking-engine shop/view activity by Summer Offers rate code in GA4 Explore.

### Remaining

* Confirm whether hotel booking-engine `purchase` events are firing in GA4.
* Confirm whether `begin_checkout` and `purchase` can receive rate/package metadata.
* Request booking-engine tracking support for deeper ecommerce attribution.
* Audit Reserve, Buy Tickets, Learn More, Check Rates, file downloads, and other outbound/vendor CTA events.
* Investigate inconsistent legacy `(not set)` event category values.
* Continue UTM/source-medium cleanup for campaign reporting.

## Recommended Booking Engine Follow-Up

Request that the booking engine tracking implementation pass rate/package context into deeper ecommerce events, especially:

* `begin_checkout`
* `purchase`

Needed fields:

* `rate_code` or `selectedRate`
* `selectedTower`
* offer/package name
* room or rate plan identifier
* transaction ID
* purchase value/revenue

Vendor/internal question:

Can the booking engine pass `rate`, `selectedRate`, and `selectedTower` from the shop URL into GA4 ecommerce events such as `begin_checkout` and `purchase`?

## Notes

This audit does not make final performance conclusions. It documents tracking readiness, metadata gaps, and validation needs for the Summer Offers reporting package.

The current tracking setup is strong enough for offer-level click and booking-engine view reporting, but not yet strong enough for confirmed offer-level checkout or revenue attribution.
