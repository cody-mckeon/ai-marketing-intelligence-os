# Tracking Health Audit

## 1. Tracking Scope

This audit covers tracking readiness for the Summer Offers page, an offer/campaign landing page launched in March that includes hotel, dining, and entertainment offers.

The reporting scope includes campaign traffic, landing page sessions, page engagement, offer/category interaction, CTA behavior, outbound/vendor link behavior, and booking, reservation, and ticketing intent. The planned reporting questions focus on whether the page is ready to support leadership conclusions about traffic quality, offer engagement, campaign behavior, CTA intent, device behavior, and third-party conversion visibility.

This audit does not assess page or campaign performance. It only assesses whether the tracking evidence needed for reporting has been provided and what must be validated before leadership reporting.

## 2. Required Tracking Inventory

The following tracking inventory should exist before the Summer Offers report is treated as trustworthy:

- Final Summer Offers page URL and any landing page variants
- Confirmed reporting date range, including whether reporting starts at the March launch date or a later campaign start date
- Page views for the final Summer Offers URL
- Landing page sessions for the final Summer Offers URL
- Scroll depth or key content exposure tracking
- Offer card click tracking
- Hotel, dining, and entertainment category interaction tracking
- Book Now click tracking
- Check Rates click tracking
- Reserve click tracking
- Buy Tickets click tracking
- Learn More click tracking
- Outbound/vendor link click tracking
- Booking flow start tracking
- Reservation flow start tracking
- Ticketing flow start tracking
- Campaign UTMs, including source, medium, campaign, content, and term where applicable
- Device category
- GA4 event names and parameters for required user actions
- GTM tags, triggers, variables, destinations, and deduplication rules for required events
- Pendo event or feature coverage if the page is instrumented there
- Paid media campaign report coverage for the same reporting window
- Vendor/platform visibility for booking engine, SevenRooms, AXS, and Fevo outcomes

Completed bookings, reservations, ticket purchases, form submissions, and revenue should only be included if confirmed through the relevant downstream vendor or platform data.

## 3. Available Tracking Evidence

No actual tracking evidence has been provided yet.

The available inputs are the approved Summer Offers Analytics Request Brief, Page Performance Analysis Plan, and Leadership Insight Summary. These documents define the intended measurement scope, required metrics, expected CTAs, likely data sources, and known caveats.

The following evidence has not been provided:

- GA4 event list or export summary
- Pendo event or feature list
- GTM tag, trigger, or variable summary
- UTM documentation
- Paid media campaign report
- Booking engine report or integration notes
- SevenRooms report or integration notes
- AXS or Fevo report or integration notes
- Manual QA notes confirming event firing

Because no direct tracking evidence has been provided, the audit cannot confirm that page views, sessions, CTA events, campaign UTMs, vendor links, or conversion paths are working.

## 4. Missing or Unconfirmed Tracking

The following items are missing or unconfirmed and must be validated before leadership reporting:

- Final Summer Offers page URL
- Any related landing page variants
- Reporting date range
- Whether the reporting window starts at the March launch date or a later campaign start date
- GA4 page and landing page reporting availability
- GA4 event names for scroll depth, offer card clicks, category interactions, CTAs, outbound/vendor links, and flow starts
- GA4 event parameters, including CTA label, offer name, offer category, destination URL, campaign fields, and device category where applicable
- GTM tags and triggers for required CTA and interaction events
- GTM deduplication rules and event destinations
- Pendo coverage for the Summer Offers page, if applicable
- Campaign UTM documentation and naming taxonomy
- Paid media campaign reports for the same reporting period
- Booking engine data availability
- SevenRooms data availability
- AXS and Fevo data availability
- Cross-domain tracking behavior for vendor destinations
- Consent behavior and its impact on observable traffic and events
- Internal traffic filtering
- Reconciliation rules between GA4, paid media platforms, and vendor reports

## 5. Event and CTA Validation Needs

The following events and CTA interactions need validation in GA4, GTM, and any applicable onsite behavior platform before they are used for reporting:

- Page view event for the final Summer Offers URL
- Landing page session attribution for campaign and non-campaign traffic
- Scroll depth tracking for key content exposure
- Offer card click events with offer name and offer category parameters
- Category interaction events for hotel, dining, and entertainment
- Book Now clicks with CTA label, offer name, offer category, and destination URL
- Check Rates clicks with CTA label, offer name, offer category, and destination URL
- Reserve clicks with CTA label, offer name, offer category, and destination URL
- Buy Tickets clicks with CTA label, offer name, offer category, and destination URL
- Learn More clicks with CTA label, offer name, offer category, and destination URL
- Outbound/vendor link clicks with destination domain and vendor/platform name
- Booking flow starts, if observable from the site or booking engine
- Reservation flow starts, if observable from the site or SevenRooms
- Ticketing flow starts, if observable from the site, AXS, or Fevo
- Device category values for desktop, mobile, and tablet reporting
- Event deduplication rules so CTA clicks and outbound/vendor clicks are not double-counted
- Cross-domain and referral handling so vendor transitions are not misclassified

CTA clicks, outbound clicks, and flow starts should be treated as onsite intent unless completed bookings, reservations, ticket purchases, form submissions, or revenue are confirmed in downstream systems.

## 6. Campaign and UTM Health

Campaign and UTM health is currently unvalidated.

The approved inputs state that campaign and UTM performance should be included in the Summer Offers reporting, but no UTM documentation, paid media report, campaign taxonomy, or campaign export has been provided yet. As a result, the audit cannot confirm whether campaign source, medium, campaign, content, or term values are present, consistent, or usable.

Before campaign reporting is presented to leadership, the team should validate:

- Campaign naming rules
- Source / medium taxonomy
- UTM coverage across paid media, email, and other campaign links
- Whether campaign links point to the final Summer Offers URL or variants
- Paid media report alignment with the GA4 reporting date range
- Whether GA4 session and campaign counts are expected to differ from ad platform clicks
- Whether missing, inconsistent, or overwritten UTMs affect source / medium conclusions

Leadership-safe caveat: campaign performance should not be summarized until UTM documentation and paid media reporting have been reviewed against GA4 campaign attribution.

## 7. Consent, Attribution, and Platform Caveats

The following caveats should be visible before any Summer Offers leadership reporting:

- Consent settings may reduce observable users, sessions, events, or campaign attribution in GA4 and other platforms.
- GA4, paid media platforms, and vendor systems may not match because they use different attribution logic, click/session definitions, conversion windows, and reporting windows.
- Cross-domain tracking may be incomplete when users move from the Summer Offers page to the booking engine, SevenRooms, AXS, Fevo, or other vendor destinations.
- Internal traffic may affect page and event reporting if filters are incomplete or not applied consistently.
- Reporting window differences may create mismatches between GA4, paid media reports, and vendor outcomes.
- Pendo coverage may be unavailable or incomplete if the Summer Offers page is not instrumented there.
- Event parameters may be missing or inconsistent, limiting offer-level, category-level, CTA-level, or destination-level analysis.
- CTA click volume should not be interpreted as completed conversion volume.

Before this can be used for leadership reporting, tracking evidence needs to be validated across GA4, GTM, campaign UTMs, paid media reports, and relevant vendor platforms.

## 8. Third-Party and Vendor Visibility

Third-party and vendor visibility is currently unconfirmed.

The Summer Offers page may send users into vendor or third-party experiences for booking, dining reservations, and entertainment ticketing. Without vendor data or integration evidence, onsite actions must be separated from completed outcomes.

- Booking engine: Book Now, Check Rates, outbound booking clicks, or booking flow starts may show hotel booking intent. They do not confirm completed bookings or revenue unless booking engine outcome data is available for the same reporting period.
- SevenRooms: Reserve clicks or reservation flow starts may show dining reservation intent. They do not confirm completed dining reservations or revenue unless SevenRooms data is available and reconcilable.
- AXS / Fevo: Buy Tickets clicks or ticketing flow starts may show entertainment ticketing intent. They do not confirm completed ticket purchases or ticket revenue unless AXS or Fevo data is available and reconcilable.
- Other vendor destinations: Learn More or outbound/vendor links may show interest or handoff behavior. They should not be treated as completed conversions without downstream confirmation.

The report can describe onsite intent once events are validated, but completed bookings, reservations, ticket purchases, form submissions, and revenue require vendor/platform evidence.

## 9. Reporting Readiness Assessment

Status: Not Ready - Missing Data

Reason: The approved brief, page performance plan, and leadership summary define the measurement scope, but no direct tracking evidence has been provided. There are no GA4 exports, Pendo exports, GTM tag summaries, UTM docs, paid media reports, vendor reports, or manual QA notes confirming that required page, campaign, CTA, event, consent, or third-party tracking is in place and trustworthy.

Leadership reporting should wait until the required tracking evidence is collected and validated. If a leadership update is needed before validation is complete, it should be framed as a measurement readiness update, not a performance conclusion.

## 10. Recommended Next Actions

- Confirm the final Summer Offers page URL and any landing page variants.
- Confirm the exact reporting date range, including whether reporting starts at the March launch date or a later campaign start date.
- Pull GA4 page, landing page, event, source / medium, campaign, and device data for the confirmed reporting window.
- Export or document GA4 event names and parameters for required Summer Offers interactions.
- Validate GTM tags, triggers, variables, destinations, and deduplication rules for page views, scroll depth, offer card clicks, category interactions, CTA clicks, outbound/vendor links, and flow starts.
- Check whether the Summer Offers page has Pendo event or feature coverage.
- Review campaign UTM documentation, source / medium taxonomy, campaign naming, and link coverage.
- Collect paid media reports for the same reporting period.
- Confirm booking engine data access and whether completed bookings or revenue can be tied to the reporting window.
- Confirm SevenRooms data access and whether completed reservations can be tied to the reporting window.
- Confirm AXS and Fevo data access and whether completed ticket purchases or revenue can be tied to the reporting window.
- Review consent, cross-domain tracking, internal traffic filtering, and platform reconciliation caveats before presenting leadership conclusions.
- Keep onsite intent metrics separate from completed conversion and revenue metrics in all reporting.
