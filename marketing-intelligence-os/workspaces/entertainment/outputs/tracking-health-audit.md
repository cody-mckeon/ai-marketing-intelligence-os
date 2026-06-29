# Entertainment Tracking Health Audit

Status: Not yet validated

## Source Inputs

- Intake brief: `inputs/campaign-brief/entertainment-page-intake-brief.md`
- Page inventory: `inputs/manual-notes/entertainment-page-inventory.md`

## Initial Reporting Goal

Determine whether GA4/GTM can support reporting for Entertainment page engagement, event-level clicks, Buy Tickets intent, vendor handoffs, and ticketing attribution.

## Current Known Questions

- Can GA4 report Entertainment page traffic?
- Can GA4 identify which entertainment event was clicked?
- Can GA4 identify which venue was clicked?
- Can GA4 distinguish Buy Tickets from Learn More?
- Can GA4 identify AXS vs Fevo vs internal destination handoffs?
- Can GA4 report View More Shows interaction?
- Can ticketing purchases be connected back to Entertainment page clicks?

## Entertainment Click Tracking Finding

GA4 captures `click` events on Entertainment pages and exposes outbound destination URLs. This confirms that vendor handoffs to domains such as AXS, Booketing, and Zouk Group are visible in GA4.

However, `Link text` is empty in Explore, and the existing click event does not expose standardized metadata for CTA type, entertainment event name, venue, category, or destination vendor.

As a result, the existing GA4 click event supports directional outbound-click reporting, but not clean CTA-level or event-level ticketing-intent reporting.

## Confirmed GTM Findings

GTM contains Entertainment-related tags, but the visible tags are primarily ad platform and vendor conversion tags rather than standardized GA4 reporting tags.

Observed tags include:

- `CM - Floodlight - Entertainment - PageView`
- `gAds - Conversion - Entertainment - Buy Tickets Button Click`
- `Facebook - Event - Zouk Entertainment Pageview`
- `nightlife - Zouk_Entertainment_Page View`
- `Tiktok Pixel Entertainment Page View`
- `Facebook - Event - AXS Added Value Booking`
- `Booketing - Booketing_Add To Cart`
- `Booketing - Booketing_Event Page View`
- `Booketing - Booking_Ticket Purchase`
- `Facebook - Event - Booketing Add to Cart`
- `Facebook - Event - Booketing Ticket Purchase`
- `Facebook - Event - Zouk Added Value Purchase Complete`

GTM also contains an existing trigger named:

- `Entertainment Buy Tickets Button Click`

This suggests that Buy Tickets interactions are already detectable in GTM, but the current visible implementation appears focused on ad/conversion platforms rather than GA4 reporting readiness.

No dedicated GA4 Entertainment CTA event tag was confirmed in this search.

## Confirmed GTM Finding: Entertainment Buy Tickets Trigger

GTM contains an existing trigger named `Entertainment Buy Tickets Button Click`.

The trigger is a Custom Event trigger using event name `click` and fires when:

- `Click Text` contains `BUY TICKETS`
- `Page Path` contains `/entertainment`

This confirms that GTM can detect Buy Tickets intent on Entertainment pages.

However, the trigger does not inspect Click URL or destination domain, so it cannot distinguish AXS, Booketing, Zouk Group, Fevo, or other vendors. It also does not provide event name, venue, category, or standardized CTA metadata by itself.

The trigger is reusable as the foundation for a GA4 Entertainment CTA event, but additional event parameters are needed for reporting.


## Confirmed GTM Validation: Entertainment Buy Tickets Click

A new GA4 event tag, `GA4 - Entertainment - Buy Tickets Click`, was created and validated in GTM Preview.

The tag sends the GA4 event:

`entertainment_buy_tickets_click`

Validated metadata includes:

- `page_location`
- `page_type`
- `cta_text`
- `cta_type`
- `link_url`
- `destination_url`
- `destination_domain`
- `destination_vendor`
- `component_name`

The tag successfully fired for Entertainment Buy Tickets / Get Tickets clicks across the following vendor patterns:

- AXS → `destination_vendor = axs`
- Booketing / UrVenue → `destination_vendor = urvenue`
- Zouk Group → `destination_vendor = zouk_group`
- SevenRooms → `destination_vendor = sevenrooms`

This improves Entertainment reporting readiness from generic click reporting to standardized ticketing-intent and vendor-handoff reporting.

Remaining limitations:

- Event name is not yet standardized as a parameter.
- Venue name is not yet standardized as a parameter.
- Artist/show name is not yet standardized as a parameter.
- Event date is not yet standardized as a parameter.
- Ticketing purchase attribution is not yet confirmed.

## Status

Tracking readiness: Partially ready for Entertainment ticketing-intent reporting

Safe to report:
- Entertainment page traffic
- Entertainment detail page traffic
- Entertainment outbound click activity
- Entertainment Buy Tickets / Get Tickets clicks
- Destination vendor handoffs for AXS, UrVenue/Booketing, Zouk Group, and SevenRooms

Not ready:
- Clean event-name-level reporting
- Venue-level ticketing intent
- Artist/show-level ticketing intent
- Event-date-level reporting
- Ticketing purchase attribution