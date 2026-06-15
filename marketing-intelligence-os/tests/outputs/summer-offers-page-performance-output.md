# Page Performance Analysis Plan

## 1. Page Purpose

The Summer Offers page should be evaluated as an offer/campaign landing page. From a business perspective, the page is meant to drive qualified engagement and booking-intent behavior across hotel, dining, and entertainment offers. From a user perspective, the page should help visitors discover relevant seasonal offers, compare offer categories, and move into the appropriate booking, reservation, ticketing, or vendor flow.

This plan defines what should be measured. It does not make performance claims because actual analytics, campaign, and vendor data have not been provided.

## 2. Primary User Actions

- View the Summer Offers landing page
- Scroll to key offer content
- Click offer cards
- Click hotel, dining, or entertainment offer categories
- Click Book Now
- Click Check Rates
- Click Reserve
- Click Buy Tickets
- Click Learn More
- Click outbound/vendor links
- Start booking flow
- Start reservation flow
- Start ticketing flow

Intent actions, such as CTA clicks and flow starts, should be reported separately from completed bookings, reservations, ticket purchases, or revenue.

## 3. Measurement Questions

- How much traffic did the Summer Offers page receive during the reporting period?
- Which traffic sources, mediums, and campaigns drove visits to the page?
- Was traffic quality strong based on engagement rate, engaged sessions, average engagement time, scroll behavior, and exit behavior?
- Which offer categories generated the most user interest: hotel, dining, or entertainment?
- Which offers or offer cards received the most engagement?
- Which CTAs drove booking, reservation, ticketing, or outbound intent?
- Did users start booking, reservation, or ticketing flows after engaging with the page?
- How did campaign and UTM-tagged traffic behave compared with other traffic?
- How did behavior differ by device category?
- Which parts of the analysis require tracking validation or third-party vendor data before conclusions can be trusted?

## 4. Recommended Metrics

- Sessions
- Users
- Engaged sessions
- Engagement rate
- Average engagement time
- Landing page sessions
- Page views
- Scroll depth
- Offer card clicks
- Offer/category engagement
- CTA clicks
- CTA click-through rate
- Outbound clicks
- Booking intent clicks
- Reservation intent clicks
- Ticket intent clicks
- Booking flow starts
- Reservation flow starts
- Ticketing flow starts
- Traffic source / medium
- Campaign / UTM performance
- Device category
- New vs returning users
- Exit rate, if available

Completed bookings, reservations, ticket purchases, and revenue should only be included if reliable booking engine, SevenRooms, AXS / Fevo, or other vendor data is available for the same reporting period.

## 5. CTA and Event Tracking Requirements

Validate that GA4 and GTM can capture the key page events before using them in the analysis.

Required or recommended tracking includes:

- Page view and landing page session tracking for the final Summer Offers URL
- Scroll depth tracking for key content exposure
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
- UTM capture for campaign, source, medium, content, and term where available

Tracking validation should confirm event names, parameters, destinations, deduplication rules, and whether events fire consistently across desktop and mobile. CTA and flow-start events should be labeled as intent unless they can be tied to completed transactions in downstream systems.

## 6. Data Sources Needed

- GA4 for sessions, users, landing page sessions, engagement, page views, source / medium, campaign / UTM performance, device behavior, CTA events, outbound clicks, and exit behavior if available
- Pendo for onsite behavior, feature interaction, or additional product/page analytics if the Summer Offers experience is tracked there
- GTM for validating CTA, scroll, offer card, outbound, booking intent, reservation intent, and ticket intent event tracking
- Booking engine for hotel booking flow starts, booking completions, or booking revenue if available
- SevenRooms for dining reservation intent, reservation completions, or dining conversion detail if available
- AXS / Fevo for entertainment ticketing intent, ticket purchases, or ticketing conversion detail if available
- Paid media reports for channel delivery, clicks, spend, campaign naming, and platform-reported performance
- Campaign UTM documentation for source / medium rules, campaign names, taxonomy, and launch context
- Campaign or offer documentation identifying the final page URL, included hotel/dining/entertainment offers, CTA definitions, and intended conversion destinations

## 7. Segments and Breakdowns

- Date range, including launch period versus later campaign periods if relevant
- Traffic source / medium
- Campaign / UTM campaign
- Paid versus organic traffic
- Device category
- New versus returning users
- Offer category: hotel, dining, entertainment
- Individual offer or offer card
- CTA type: Book Now, Check Rates, Reserve, Buy Tickets, Learn More, outbound/vendor link
- Audience or geo segment, if available and relevant
- Landing page variants, if multiple URLs or campaign variants exist

## 8. Data Caveats and Risks

- The final page URL is missing and must be confirmed before analysis.
- The exact reporting date range is missing, including whether the analysis starts at the March launch date or a later campaign start date.
- CTA/event definitions are missing and must be confirmed before interpreting event volume.
- Event names are missing and should be validated in GA4 and GTM.
- UTM documentation is missing or unconfirmed, which may limit campaign reporting accuracy.
- Vendor data availability is unconfirmed for the booking engine, SevenRooms, and AXS / Fevo.
- Third-party booking, reservation, and ticketing platforms may limit visibility from page engagement to completed bookings, reservations, ticket purchases, or revenue.
- CTA clicks, outbound clicks, and flow starts indicate intent and should not be treated as completed conversions without downstream data.
- GA4, paid media platforms, and vendor systems may not match because of attribution logic, consent behavior, click/session definitions, and reporting windows.
- Consent settings, internal traffic, cross-domain tracking, or missing GTM tags may reduce observable behavior.
- Pendo coverage may be unavailable or incomplete if the Summer Offers page is not instrumented there.

## 9. Analysis Output Structure

The final page performance report should use this structure:

- Executive summary with key findings and caveats
- Page purpose and measurement scope
- Traffic overview
- Engagement overview
- Campaign and UTM performance
- Offer/category engagement
- CTA and booking-intent behavior
- Device behavior
- Third-party/vendor conversion visibility
- Data quality, tracking validation, and caveats
- Recommended next actions

The report should keep measurement findings separate from interpretation and should clearly label which results are based on page analytics, intent clicks, and downstream conversion data.

## 10. Next Agent to Run

After the page performance plan is complete and available data has been gathered or exported, run the Leadership Insight Agent to turn the findings, caveats, and recommended next actions into a concise leadership-ready narrative.
