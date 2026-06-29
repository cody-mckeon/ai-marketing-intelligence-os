# Sitewide Tracking Readiness Index

Status: Draft created from approved orchestrator proposal  
Workspace: `workspaces/sitewide-tracking-readiness/`  
Scope: Sitewide tracking-readiness classification across major RWLV page families and conversion paths.

## Purpose

This index summarizes which RWLV website page families currently have evidence-supported tracking readiness and which page families still require inventory, GA4 review, GTM audit, validation, or vendor evidence before leadership reporting can rely on them.

This is a readiness index only. It does not audit every page yet and does not make performance conclusions.

## Evidence Guardrails

This index uses only existing evidence from:

- `IDEA.md`
- `.hermes.md`
- `docs/marketing-intelligence-os-operating-model.md`
- `docs/hermes-agent-ecosystem-map.md`
- `workspaces/summer-offers/`
- `workspaces/entertainment/`
- Existing `workspaces/sitewide-tracking-readiness/sitewide-tracking-readiness-index.md`

Do not infer or invent:

- GA4 events, parameters, custom dimensions, Explore findings, Realtime findings, or standard-report availability
- GTM tags, triggers, variables, lookup tables, Preview results, or publish status
- Vendor-side outcomes
- Purchases
- Reservations
- Booking attribution
- Ticketing attribution
- Revenue attribution

Validated examples should be treated as proof of workflow pattern and page-family-specific readiness only:

- Summer Offers
- Entertainment

All other page families are classified as `Not ready` or `Not yet audited` unless evidence exists in the current repo.

## Readiness Definitions

| Status | Meaning |
|---|---|
| Ready | Existing evidence supports the reporting claim with acceptable confidence. |
| Ready with caveats | Evidence supports directional or limited reporting, but known limitations remain. |
| Partially ready | Some funnel steps or claims are validated, but the full reporting claim is not supported. |
| Not ready | Existing evidence does not support the reporting claim. |
| Vendor dependency | Reporting depends on third-party platform, vendor-side tracking, or downstream outcome evidence. |
| Not yet audited | No workspace-level evidence has been reviewed yet for this page family. Treat as not ready for reporting until audited. |

## Sitewide Readiness Summary

| Page family | Primary user actions | Key vendors / systems | Current evidence | Readiness | Safe to report now | Do not claim yet | Next action |
|---|---|---|---|---|---|---|---|
| Summer Offers | Book Now, Learn More, PDF/menu clicks, booking-engine handoff | Booking engine, GA4, GTM | Validated workspace exists at `workspaces/summer-offers/`. Evidence supports enhanced `book_now_offer_click`, offer metadata, rate-code handoff, destination/vendor handoff, booking-engine `view_item` activity by Summer Offers rate code, and general booking-engine `begin_checkout` activity. | Partially ready | Offer-level Book Now clicks; offer-category clicks; rate-code handoffs; destination/vendor handoffs; booking-engine `view_item` activity by Summer Offers rate code; directional page traffic and source/medium reporting with caveats. | Offer-level checkout attribution; offer-level hotel purchase attribution; offer-level hotel revenue attribution; full Summer Offers revenue attribution. | Request or validate booking-engine support for passing rate/package context into `begin_checkout` and `purchase`; confirm hotel booking-engine purchase events before revenue reporting. |
| Entertainment | Buy Tickets, Get Tickets, Learn More, Tables, filters, event-card clicks | AXS, Booketing / UrVenue, Zouk Group, SevenRooms, GA4, GTM | Validated workspace exists at `workspaces/entertainment/`. Evidence supports Entertainment page traffic, detail-page traffic, generic outbound clicks, GTM Preview validation for `entertainment_buy_tickets_click`, GA4 Realtime receipt of the event, and destination-vendor metadata for Buy Tickets / Get Tickets handoffs. | Partially ready | Entertainment page traffic; detail-page traffic; filtered page states directionally; generic outbound destination analysis with caveats; Buy Tickets / Get Tickets onsite intent validated in GTM Preview and GA4 Realtime; vendor handoff metadata for AXS, Booketing / UrVenue, Zouk Group, and SevenRooms. | GA4 Explore / standard reporting readiness for the new event unless post-processing evidence exists; event-name-level intent; venue-level intent; artist/show-level performance; event-date reporting; category reporting; Learn More reporting; Tables reporting; ticket purchases; reservations; ticketing or reservation revenue attribution. | Validate `entertainment_buy_tickets_click` in GA4 Explore after processing, then add standardized event-context parameters such as event name, venue, artist/show, event date, and category. |
| Dining | Reserve, Learn More, menu downloads, dining event clicks | SevenRooms, OpenTable or other reservation vendors if present, internal pages, PDFs | No dedicated Dining workspace evidence reviewed in this OS. Entertainment evidence includes SevenRooms as an Entertainment dining-event vendor handoff, but that does not validate Dining page-family tracking. | Not yet audited / Not ready | None from this sitewide index. | Reservation attribution; dining revenue; SevenRooms reservations; menu-download attribution; offer/event-level dining performance. | Start Dining page-family inventory before GA4 or GTM claims. |
| Rooms / Hotel | Check Rates, Book Now, room-detail views, tower selection, booking-engine handoff | Booking engine, hotel/tower pages, GA4, GTM | Summer Offers confirms booking-engine activity and rate-code visibility for that campaign path only. No broad Rooms / Hotel page-family audit exists in the current evidence. | Not yet audited / Not ready | None for the general Rooms / Hotel family from this index. | Room-level booking attribution; tower-level booking attribution; general hotel purchases; room revenue; booking-engine purchase attribution. | Start Rooms / Hotel page-family inventory and booking-engine tracking map. |
| Homepage | Booking widget, Book Your Stay, promo CTAs, navigation clicks, campaign modules | Booking engine, internal pages, campaign landing pages | Existing sitewide index says Homepage was not audited in this OS. No workspace-level evidence was reviewed. | Not yet audited / Not ready | None from this sitewide index. | Homepage CTA performance; booking-start attribution; promo-module attribution; revenue influence. | Inventory homepage CTAs, booking widget behavior, promo modules, and destination paths. |
| Meetings & Events | Submit inquiry, brochure/PDF downloads, Learn More, venue-detail actions | Forms, sales systems, PDFs, internal pages | Existing sitewide index says Meetings & Events was not audited. No workspace-level evidence was reviewed. | Not yet audited / Not ready | None from this sitewide index. | Lead attribution; form-submit attribution; brochure-download attribution; sales-pipeline impact; event revenue. | Start Meetings & Events page-family inventory and form/vendor mapping. |
| Offers, excluding Summer Offers | Book Now, Learn More, offer-detail views, booking-engine handoff | Booking engine, internal offer pages, GA4, GTM | Summer Offers is validated as one offer/campaign example. No evidence confirms that all other offer pages share the same metadata, rate-code mapping, GTM behavior, GA4 custom dimensions, or booking-engine attribution path. | Not yet audited / Not ready | None for non-Summer Offers offer pages from this index. | Offer-level attribution for other offers; checkout attribution; hotel purchases; revenue attribution. | Use Summer Offers as the validated pattern, then audit the next offer page or campaign separately. |
| Nightlife / Dayclub outside Entertainment listing | Get Tickets, Tables, event-detail clicks, vendor handoffs | Zouk Group, possible reservation/table systems | Entertainment evidence includes Zouk Group vendor handoffs from the Entertainment page. That does not validate standalone nightlife/dayclub page tracking or table/reservation outcomes. | Not yet audited / Not ready | None outside the Entertainment evidence scope. | Table reservations; ticket purchases; revenue attribution; artist/event-level performance outside validated Entertainment paths. | Inventory nightlife/dayclub page paths and determine whether they reuse Entertainment tracking or need separate CTA events. |
| Dining events inside Entertainment | Buy Tickets, Learn More, reservations | SevenRooms, internal pages | Entertainment workspace validates SevenRooms as a destination-vendor lookup for Entertainment Buy Tickets / Get Tickets handoffs. It does not validate reservation completion or Dining page-family reporting. | Ready with caveats for Entertainment vendor handoff only; otherwise Not ready | Onsite Entertainment handoff intent to SevenRooms when using the validated Entertainment Buy/Get Tickets event. | Completed reservations; dining revenue; vendor-side attribution; Dining page-family reporting. | Keep this scoped to Entertainment until Dining and SevenRooms outcomes are audited separately. |
| File downloads / PDFs | Menu downloads, brochures, PDFs | Internal files, GA4 file download events if present | Summer Offers page inventory identified PDF menu links and the tracking health audit notes that file-download reporting still needs review. No validated file-download metadata evidence was found. | Not ready | None from this index. | PDF engagement by offer/page family; menu-download attribution; brochure-download attribution. | Audit GA4 file-download events and required metadata such as file name, page family, CTA text, offer/event context, and destination. |
| Generic outbound clicks sitewide | Outbound vendor clicks | GA4 enhanced measurement or custom click tracking | Entertainment evidence shows generic GA4 `click` events can expose `Link URL` and `Outbound` status for Entertainment pages, but `Link text` was empty and metadata was incomplete. This does not validate clean sitewide CTA reporting. | Ready with caveats only where page-specific evidence exists; otherwise Not ready | Broad destination-domain analysis on validated pages only, with caveats. | Clean CTA reporting; event-level attribution; vendor outcome attribution; sitewide conversion reporting. | Do not use generic click volume as clean CTA reporting. Audit page-family-specific metadata before reporting CTA performance. |

## Validated Example 1: Summer Offers

Workspace:

```text
workspaces/summer-offers/
```

Validated readiness:

- Directional Summer Offers page traffic reporting
- Source / medium reporting with caveats
- Basic event-volume reporting
- Enhanced `book_now_offer_click`
- Offer-level Book Now clicks
- Offer-category Book Now clicks
- Rate-code handoffs
- Destination/vendor reporting for Book Now CTAs
- Booking-engine `view_item` activity by Summer Offers rate code
- General booking-engine `begin_checkout` activity

Key validated metadata includes:

- `offer_name`
- `offer_category`
- `rate_code`
- `destination_vendor`
- `cta_type`
- `component_name`
- `cta_text`
- `link_url`
- `destination_url`
- `destination_domain`
- `tower`

Remaining gaps:

- Summer Offers rate-code context does not appear to persist into checkout page locations.
- Offer-level checkout attribution is not confirmed.
- Offer-level hotel purchase attribution is not confirmed.
- Offer-level hotel revenue attribution is not confirmed.
- Hotel booking-engine `purchase` events were not confirmed in the reviewed evidence.

Classification:

```text
Partially ready
```

Leadership-safe interpretation:

Summer Offers can support offer-level click and booking-engine shop/view reporting, but not confirmed offer-level checkout, purchase, or revenue attribution.

## Validated Example 2: Entertainment

Workspace:

```text
workspaces/entertainment/
```

Validated readiness:

- Entertainment page traffic
- Entertainment detail-page traffic
- Filtered Entertainment page states directionally where URLs expose filter state
- Generic outbound link visibility with caveats
- Published / validated GA4 event: `entertainment_buy_tickets_click`
- GTM Preview validation for Buy Tickets / Get Tickets clicks
- GA4 Realtime receipt of `entertainment_buy_tickets_click`
- Destination vendor handoffs for:
  - AXS
  - Booketing / UrVenue
  - Zouk Group
  - SevenRooms

Validated event parameters include:

- `page_location`
- `page_type`
- `cta_text`
- `cta_type`
- `link_url`
- `destination_url`
- `destination_domain`
- `destination_vendor`
- `component_name`

Remaining gaps:

- GA4 Explore / standard reporting readiness for the new event is not confirmed in the workspace evidence.
- Standardized Entertainment event name is not captured.
- Standardized venue name is not captured.
- Standardized artist/show name is not captured.
- Standardized event date is not captured.
- Standardized Entertainment category is not captured.
- Learn More and Tables CTA tracking is not validated as standardized reporting.
- Filter interaction events are not validated.
- Vendor-side purchases, reservations, transaction IDs, and revenue are not confirmed.

Classification:

```text
Partially ready
```

Leadership-safe interpretation:

Entertainment tracking is partially ready for traffic, detail-page, ticketing-intent, and vendor-handoff reporting, but not ready for event-level, venue-level, artist/show-level, event-date-level, purchase, reservation, or revenue attribution.

## Reporting Rules

### Safe to report from validated examples

Summer Offers:

- Summer Offers traffic, directionally
- Source / medium mix with caveats
- Offer-level Book Now clicks
- Offer-category Book Now clicks
- Rate-code handoffs
- Destination/vendor handoffs
- Booking-engine `view_item` activity by Summer Offers rate code

Entertainment:

- Entertainment page traffic
- Entertainment detail-page traffic
- Filtered page states where URL states exist, directionally
- Generic outbound destination analysis with caveats
- Buy Tickets / Get Tickets onsite intent from the validated event, with GA4 Realtime caveat
- Destination vendor handoffs for the validated Entertainment Buy/Get Tickets event, with GA4 Explore caveat

### Directional only

- Generic outbound click activity where only `Link URL` and `Outbound` are visible
- Filtered page-state traffic where filter choices appear in the URL
- Detail-page traffic as a proxy for interest, not conversion
- Booking-engine view/shop activity by rate code where validated, not checkout or purchase

### Do not claim yet

- Sitewide CTA performance
- Sitewide booking attribution
- Sitewide reservation attribution
- Sitewide ticket purchase attribution
- Sitewide revenue attribution
- Vendor-side completed purchases
- Vendor-side completed reservations
- Offer-level hotel purchases
- Entertainment ticketing revenue
- Dining reservation revenue
- Meeting lead quality or sales pipeline impact
- Homepage influence on bookings or revenue

## Recommended Next Action

Do not audit every page yet.

Recommended next action:

```text
Choose one next page family for a controlled inventory and evidence review.
```

Suggested priority:

1. Dining, if reservation attribution is the next business priority.
2. Rooms / Hotel, if booking-engine attribution is the next business priority.
3. Homepage, if sitewide entry-point CTA tracking is the next business priority.

For the selected page family, run the workflow in this order:

1. Page inventory
2. GA4 evidence review
3. GTM tracking audit
4. Tracking readiness classification
5. One recommended fix or validation step

## Run Summary

### What was updated

- Created the proposed workspace folder structure under `workspaces/sitewide-tracking-readiness/`.
- Wrote `workspaces/sitewide-tracking-readiness/outputs/sitewide-tracking-readiness-index.md`.
- Verified `.hermes.md` exists at `marketing-intelligence-os/.hermes.md` and included it as evidence.
- Did not modify the existing root-level `workspaces/sitewide-tracking-readiness/sitewide-tracking-readiness-index.md`.

### Evidence used

- `IDEA.md`
- `.hermes.md`
- `docs/marketing-intelligence-os-operating-model.md`
- `docs/hermes-agent-ecosystem-map.md`
- `agents/hermes-marketing-intelligence-orchestrator.md`
- Existing `workspaces/sitewide-tracking-readiness/sitewide-tracking-readiness-index.md`
- `workspaces/summer-offers/outputs/tracking-health-audit.md`
- `workspaces/summer-offers/inputs/manual-notes/summer_offers_booking_and_attribution.md`
- `workspaces/summer-offers/inputs/manual-notes/summer-offers-page-tracking-audit.md`
- `workspaces/summer-offers/inputs/manual-notes/gtm_book-now-offer-click_preview-validation.md`
- `workspaces/entertainment/outputs/tracking-health-audit.md`
- `workspaces/entertainment/inputs/entertainment-page-inventory.md`
- `workspaces/entertainment/inputs/ga4/entertainment-event-discovery.md`
- `workspaces/entertainment/inputs/ga4/entertainment-buy-tickets-ga4-realtime-validation.md`
- `workspaces/entertainment/inputs/gtm/entertainment-buy-tickets-gtm-validation.md`

### Still missing

- No dedicated Dining workspace evidence.
- No dedicated Rooms / Hotel workspace evidence.
- No Homepage workspace evidence.
- No Meetings & Events workspace evidence.
- No broad sitewide GA4/GTM audit evidence.
- No sitewide vendor-side purchase, reservation, transaction, or revenue evidence.

### Next recommended action

- Choose one next page family for a controlled inventory and evidence review before expanding the sitewide audit.
