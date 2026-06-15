# Data Source Map

## 1. Reporting Objective

This Data Source Map supports the Summer Offers page/campaign reporting workflow. The reporting objective is to identify the data sources needed to evaluate Summer Offers traffic, engagement, campaign performance, CTA/intent behavior, and visibility into completed booking, dining reservation, and entertainment ticketing outcomes.

The Summer Offers page launched in March and includes hotel, dining, and entertainment offers. The planned report is intended for marketing leadership, website/product stakeholders, campaign owners, channel managers, and agency partners.

No actual GA4 export, Pendo export, GTM tag summary, UTM documentation, paid media report, email report, booking engine report, SevenRooms report, AXS / Fevo report, or vendor conversion data has been provided yet. This map identifies what should be pulled and validated before performance conclusions are made.

## 2. Required Data Sources

### GA4

- Source name: GA4
- Purpose: Source of truth for website traffic, acquisition, landing page sessions, engagement, device behavior, campaign attribution where UTMs are present, and configured onsite events.
- What it can answer: Sessions, users, landing page sessions, source / medium, campaign values, device category, engaged sessions, engagement rate, average engagement time, page views, and configured event counts for CTAs or onsite interactions if tracking exists.
- What it cannot answer: Completed hotel bookings, dining reservations, ticket purchases, vendor revenue, or platform-reported ad delivery unless those systems are integrated and validated.

### Pendo

- Source name: Pendo
- Purpose: Supplemental onsite behavior and feature/event interaction source if the Summer Offers page is instrumented there.
- What it can answer: Feature interactions, guide/module engagement, click patterns, scroll or page behavior, and product-style engagement if configured.
- What it cannot answer: Traffic acquisition, paid media delivery, GA4 sessions, or completed vendor outcomes.

### GTM

- Source name: GTM
- Purpose: Tracking implementation and validation source for tags, triggers, variables, event definitions, event parameters, destinations, and deduplication.
- What it can answer: Whether required tracking is configured for page views, scroll depth, offer card clicks, category interactions, CTAs, outbound/vendor links, and flow starts.
- What it cannot answer: Performance results by itself. GTM is not a reporting tool and does not replace GA4, Pendo, paid media, or vendor reports.

### Paid Media Platforms

- Source name: Paid media platforms
- Purpose: Source of truth for platform delivery metrics and paid campaign metadata if paid media was active.
- What it can answer: Spend, impressions, reach, clicks, CTR, CPC, frequency, placements, campaign names, ad sets, ads, creative, and platform-reported conversions if configured.
- What it cannot answer: GA4 sessions, GA4 engagement, onsite behavior, completed bookings, dining reservations, ticket purchases, or revenue outside the platform attribution model.

### UTM Documentation

- Source name: UTM documentation
- Purpose: Source of truth for campaign taxonomy, naming conventions, link tagging, and source / medium consistency.
- What it can answer: Intended campaign, source, medium, content, term, channel, and naming rules for Summer Offers links.
- What it cannot answer: Actual traffic, engagement, delivery, or conversion performance.

### Campaign Brief

- Source name: Campaign brief
- Purpose: Source of truth for the campaign context, page URL, included offers, intended audiences, channels, launch timing, and business goals.
- What it can answer: What Summer Offers was intended to promote, which hotel/dining/entertainment offers were in scope, which CTAs and destinations were expected, and which channels were planned.
- What it cannot answer: Actual traffic, engagement, campaign delivery, or conversion outcomes.

### Email Platform

- Source name: Email platform
- Purpose: Source of truth for email campaign delivery and link engagement if email was active for Summer Offers.
- What it can answer: Sends, delivered emails, opens, clicks, click-through rate, unsubscribes, email campaign names, link-level performance, and audience/segment detail if available.
- What it cannot answer: GA4 sessions, onsite engagement, completed vendor outcomes, or revenue unless downstream tracking and reconciliation exist.

### Booking Engine

- Source name: Booking engine
- Purpose: Source of truth for completed hotel booking outcomes and hotel revenue if available.
- What it can answer: Booking completions, booking dates, room/revenue fields, offer codes, package or rate plan usage, and possibly booking flow starts if the vendor provides that data.
- What it cannot answer: GA4 traffic acquisition, paid media delivery, onsite engagement before handoff, or dining/ticketing outcomes.

### SevenRooms

- Source name: SevenRooms
- Purpose: Source of truth for completed dining reservation outcomes if RWLV has access.
- What it can answer: Reservation completions, reservation date/time, venue, party size, campaign or source fields if available, and dining conversion outcomes.
- What it cannot answer: GA4 traffic, onsite engagement, paid delivery, hotel bookings, ticket purchases, or revenue unless provided in the SevenRooms export.

### AXS / Fevo

- Source name: AXS / Fevo
- Purpose: Source of truth for entertainment ticketing outcomes if available.
- What it can answer: Ticket purchases, event names, order counts, ticket quantity, ticket revenue, promo/campaign fields if available, and ticketing conversion outcomes.
- What it cannot answer: GA4 traffic, onsite engagement, paid delivery, hotel bookings, or dining reservations.

### Manual Analyst Notes / QA

- Source name: Manual analyst notes / QA
- Purpose: Supports source interpretation, tracking validation, screenshots, access notes, and reconciliation decisions.
- What it can answer: Whether exports were pulled, who provided them, whether event firing was manually checked, which access gaps remain, and which caveats should be attached to the report.
- What it cannot answer: Source-system metrics unless those metrics are backed by actual exports or screenshots.

## 3. Metric-to-Source Map

### Delivery Metrics

- Impressions: Paid media platforms, email platform if active, social platform if active
- Reach: Paid media platforms or social platform if active
- Spend: Paid media platforms or agency report
- Clicks: Paid media platforms, email platform if active, social platform if active
- Click-through rate: Paid media platforms, email platform if active, social platform if active
- Cost per click: Paid media platforms or agency report
- Frequency: Paid media platforms if available
- Source of truth: The delivery platform or agency report for the channel

Delivery clicks should not be treated as GA4 sessions.

### Traffic Metrics

- Sessions: GA4
- Users: GA4
- New users: GA4
- Landing page sessions: GA4
- Source / medium: GA4, interpreted against UTM documentation
- Campaign / UTM performance: GA4, interpreted against UTM documentation and campaign brief
- Device category: GA4
- Source of truth: GA4 for website traffic and acquisition metrics

### Engagement Metrics

- Engaged sessions: GA4
- Engagement rate: GA4
- Average engagement time: GA4
- Page views: GA4
- Scroll depth: GA4 if configured, GTM for validation, Pendo if instrumented
- Offer card clicks: GA4 events if configured, GTM for validation, Pendo if instrumented
- Offer/category engagement: GA4 events if configured, GTM for validation, Pendo if instrumented
- Source of truth: GA4 for standard engagement metrics; GA4/Pendo for configured onsite behavior depending on instrumentation

### CTA / Intent Metrics

- CTA clicks: GA4 events if configured, GTM for validation, Pendo if instrumented
- CTA click-through rate: GA4 calculated from CTA events and relevant page/session denominator
- Book Now clicks: GA4 events if configured, GTM for validation
- Check Rates clicks: GA4 events if configured, GTM for validation
- Reserve clicks: GA4 events if configured, GTM for validation
- Buy Tickets clicks: GA4 events if configured, GTM for validation
- Learn More clicks: GA4 events if configured, GTM for validation
- Outbound/vendor clicks: GA4 events if configured, GTM for validation
- Booking, reservation, and ticketing flow starts: GA4 if tracked before handoff or relevant vendor platform if provided
- Source of truth: GA4 for onsite intent event counts after GTM validation; Pendo only if instrumented and reconciled

CTA clicks, outbound clicks, and flow starts are intent metrics only. They are not completed conversions.

### Conversion Metrics

- Completed hotel bookings: Booking engine
- Completed dining reservations: SevenRooms
- Completed ticket purchases: AXS / Fevo
- Form submissions: Ninja Forms or form platform if in scope, reconciled with GA4 form events if tracked
- Source of truth: The downstream vendor or platform where the completed action occurs

### Revenue Metrics

- Hotel booking revenue: Booking engine
- Dining revenue: SevenRooms only if revenue fields are provided and reliable
- Ticket revenue: AXS / Fevo if available
- Return on ad spend: Requires paid media spend plus confirmed revenue from the relevant downstream source
- Cost per acquisition: Requires paid media spend plus confirmed completed outcomes
- Source of truth: Vendor revenue systems for revenue; paid platforms for spend

### Tracking Validation

- Tags, triggers, variables, event names, parameters, destinations, and deduplication: GTM
- Manual event firing and QA notes: Manual analyst notes / QA
- GA4 event receipt and event counts: GA4
- Source of truth: GTM for implementation logic; GA4 for received event data

### Campaign Taxonomy

- Campaign naming rules: UTM documentation and campaign brief
- Source / medium rules: UTM documentation
- UTM campaign, content, and term values: UTM documentation and GA4 after traffic is collected
- Channel and launch context: Campaign brief
- Source of truth: UTM documentation for intended taxonomy; GA4 for observed campaign traffic

### Vendor Outcomes

- Hotel booking outcomes: Booking engine
- Dining reservation outcomes: SevenRooms
- Entertainment ticketing outcomes: AXS / Fevo
- Vendor handoff clicks: GA4/GTM if tracked
- Source of truth: Vendor platform for completed outcomes; GA4/GTM for onsite handoff intent

## 4. Required Exports or Reports

### GA4

- Traffic acquisition report by date, source / medium, campaign, and device category
- Landing page report filtered to the final Summer Offers page URL and any variants
- Events report for page views, scroll depth, offer card clicks, category interactions, CTA clicks, outbound/vendor clicks, and flow starts
- Campaign report by UTM campaign, source, medium, content, and term if available
- Device report for desktop, mobile, and tablet behavior

### Pendo

- Feature/event report for Summer Offers page behavior if instrumented
- Click, scroll, feature, guide, or module engagement report if relevant
- Screenshot or note confirming whether the Summer Offers page is covered by Pendo

### GTM

- Tag, trigger, and variable summary for Summer Offers page tracking
- Event parameter summary for CTA label, offer name, offer category, destination URL, event name, and vendor/platform destination
- QA summary or screenshots showing whether required events fire on desktop and mobile
- Deduplication and destination summary for events sent to GA4 or other tools

### Paid Media Platforms

- Paid media campaign report for the same reporting period
- Campaign, ad set, ad, creative, placement, audience, spend, impressions, reach, clicks, CTR, CPC, frequency, and platform conversion fields if configured
- Agency summary if the agency owns the media exports

### UTM Documentation

- Summer Offers UTM naming documentation
- Source / medium taxonomy
- Campaign, content, and term naming rules
- Link list showing final destination URLs and tagged URLs
- Campaign launch context and active channel list

### Campaign Brief

- Final Summer Offers page URL and any landing page variants
- Launch date and reporting date range
- List of hotel, dining, and entertainment offers
- CTA definitions and intended destination paths
- Channel plan and campaign goals
- Audience and business objective notes

### Email Platform

- Email campaign report if email was active
- Sends, delivered emails, opens, clicks, click-through rate, unsubscribes, campaign name, audience/segment, link URL, UTM values, and reporting date range

### Booking Engine

- Booking engine report for completed hotel bookings and revenue if available
- Booking date, stay date, offer name, offer category, package/rate code, source/campaign fields if available, conversion count, and revenue
- Vendor notes on attribution, cross-domain tracking, and whether Summer Offers traffic can be identified

### SevenRooms

- SevenRooms reservation report for completed dining reservations if available
- Reservation date/time, venue, offer or campaign field if available, party size, status, source field if available, and conversion count
- Vendor notes on attribution and whether Summer Offers traffic can be identified

### AXS / Fevo

- AXS / Fevo ticketing report for entertainment ticket purchases if available
- Event name, purchase date, ticket quantity, order count, revenue, campaign or promo field if available, and source field if available
- Vendor notes on attribution and whether Summer Offers traffic can be identified

### Manual Analyst Notes / QA

- Notes confirming who pulled each export and when
- Screenshots or summaries documenting access gaps
- Manual QA notes for CTA and event firing
- Reconciliation notes across GA4, paid media, Pendo, and vendor systems

## 5. Required Fields

### Core Reporting Fields

- Date
- Reporting date range
- Page path / URL
- Landing page URL
- Source / medium
- Default channel group
- Campaign
- UTM campaign
- UTM source
- UTM medium
- UTM content
- UTM term
- Device category

### Page and Engagement Fields

- Sessions
- Users
- New users
- Landing page sessions
- Page views
- Engaged sessions
- Engagement rate
- Average engagement time
- Exit rate, if available
- Scroll depth
- Offer name
- Offer category
- Offer card label or ID

### Event and CTA Fields

- Event name
- Event count
- Event parameter name/value
- CTA label
- CTA type
- Destination URL
- Destination domain
- Vendor/platform destination
- Booking flow start
- Reservation flow start
- Ticketing flow start
- Outbound click count
- Conversion count if confirmed by source of truth

### Delivery and Campaign Fields

- Platform
- Channel
- Campaign name
- Ad set or ad group
- Ad or creative name
- Audience or segment
- Placement
- Impressions
- Reach
- Clicks
- Click-through rate
- Spend
- Cost per click
- Frequency

### Vendor Outcome Fields

- Booking completion count
- Reservation completion count
- Ticket purchase count
- Form submission count, if in scope
- Revenue if available
- Order or booking ID if exportable and privacy-approved
- Offer code, rate code, promo code, or campaign field if available
- Reservation venue or event name
- Ticket quantity

### Ownership and Readiness Fields

- Source owner
- Export owner
- Access status
- Vendor contact
- Date pulled
- Data window
- Known caveats
- Reconciliation notes

## 6. Source Ownership and Access

- GA4: Likely owned by the internal website / analytics owner, website agency, or analytics/admin owner. Access is not confirmed.
- Pendo: Likely owned by the Pendo admin, product/website analytics owner, or digital product team. Coverage and access are not confirmed.
- GTM: Likely owned by the GTM/admin owner, website agency, analytics owner, or implementation partner. Access is not confirmed.
- Paid media platforms: Likely owned by the marketing campaign owner, paid media agency, or agency partner. Active channels and access are not confirmed.
- UTM documentation: Likely owned by the marketing campaign owner, paid media agency, email owner, or agency partner. Documentation has not been provided.
- Campaign brief: Likely owned by the marketing campaign owner or agency partner. Final page URL, offer list, active channels, and reporting date range still need confirmation.
- Email platform: Likely owned by the email platform owner, CRM/email marketing owner, marketing campaign owner, or agency partner. Email activity and access are not confirmed.
- Booking engine: Likely owned or accessed through the booking engine vendor, internal revenue/ecommerce owner, or website/booking partner. Access is not confirmed and may require vendor support.
- SevenRooms: Likely owned or accessed through the SevenRooms contact, dining operations/marketing owner, or vendor relationship owner. Access is not confirmed and may require vendor support.
- AXS / Fevo: Likely owned or accessed through the AXS / Fevo contact, entertainment marketing owner, ticketing owner, or vendor relationship owner. Access is not confirmed and may require vendor support.
- Manual analyst notes / QA: Likely owned by the internal analyst, analytics owner, website agency, or implementation partner. No QA notes have been provided yet.

Unknown or unconfirmed ownership should be resolved before exports are requested. Vendor contacts are especially important for booking engine, SevenRooms, and AXS / Fevo reporting.

## 7. Caveats by Source

### GA4

- GA4 traffic and engagement data has not been provided yet.
- GA4 can report sessions, users, source / medium, campaign values, landing pages, device category, engagement, and configured events, but only if the final page URL and event setup are correct.
- GA4 cannot confirm completed booking, reservation, ticketing, or revenue outcomes unless downstream systems are integrated and validated.
- GA4 may differ from paid media and vendor systems because of consent behavior, attribution logic, click/session definitions, internal traffic filtering, cross-domain tracking, and reporting windows.

### Pendo

- Pendo coverage for the Summer Offers page is not confirmed.
- Pendo may be useful for onsite behavior and feature interaction if instrumented, but it cannot replace GA4 for acquisition and traffic reporting.
- Pendo events may not use the same definitions or reporting windows as GA4 events.

### GTM

- No GTM tag, trigger, variable, or event parameter summary has been provided.
- GTM can validate implementation, but it is not a reporting source by itself.
- Events should not be trusted for reporting until firing behavior, destinations, parameters, and deduplication are validated.

### Paid Media Platforms

- Paid media reports have not been provided and active channels are not confirmed.
- Platform clicks should not be treated as GA4 sessions.
- Platform conversions, if present, may not match GA4 or vendor outcomes because of attribution windows, modeled conversions, click/view-through logic, consent, and reporting windows.

### UTM Documentation

- UTM documentation has not been provided.
- Missing or inconsistent UTMs can weaken source / medium, campaign, content, and term reporting.
- UTM documentation shows intended taxonomy, while GA4 shows observed traffic; both should be reviewed together.

### Campaign Brief

- The campaign brief or equivalent source still needs to confirm the final page URL, date range, active channels, included offers, CTA definitions, and intended destinations.
- Without a confirmed campaign brief, data pulls may use the wrong reporting window, page URL, channel list, or offer taxonomy.

### Email Platform

- Email activity is not confirmed.
- Email clicks may not match GA4 sessions because of consent, bot filtering, prefetching, attribution, and reporting window differences.
- Email should be marked not needed if no Summer Offers email campaign was active.

### Booking Engine

- Booking engine access and report availability are not confirmed.
- Booking engine data is needed for completed hotel bookings and hotel revenue.
- Cross-domain tracking and vendor attribution may limit the ability to connect Summer Offers onsite intent to completed bookings.

### SevenRooms

- SevenRooms access and report availability are not confirmed.
- SevenRooms data is needed for completed dining reservations.
- Reserve clicks or reservation flow starts from GA4 should not be treated as completed reservations.

### AXS / Fevo

- AXS / Fevo access and report availability are not confirmed.
- AXS / Fevo data is needed for completed entertainment ticket purchases and ticket revenue if available.
- Buy Tickets clicks or ticketing flow starts from GA4 should not be treated as completed ticket purchases.

### Vendor Reports

- Vendor reports may use different attribution logic, date fields, reporting windows, campaign fields, and export structures.
- Vendor reports may not include UTM fields or may require vendor support to identify Summer Offers traffic.
- Vendor outcomes should be reconciled carefully with GA4 handoff/intent events.

### Manual Analyst Notes / QA

- Manual QA notes have not been provided.
- QA notes can support tracking confidence, but they should not replace system exports.
- Screenshots and manual checks should document the date, environment, device, browser, and event behavior tested.

## 8. Manual Export Now vs Connect Later

| Source | Classification | Reason |
| --- | --- | --- |
| GA4 | Manual export now | GA4 is required for traffic, acquisition, engagement, landing page, campaign, device, and event data. Pull manual exports first because the report is not yet a confirmed recurring connection need. |
| Pendo | Manual export now | Pull only if the Summer Offers page is instrumented. If coverage is not confirmed, first request a coverage screenshot or admin confirmation. |
| GTM | Manual QA now | GTM should be reviewed for tags, triggers, variables, parameters, destinations, and deduplication before event data is trusted. |
| Paid media platforms | Manual export now | Pull paid media or agency reports if paid channels were active. Delivery metrics are needed but should remain separate from GA4 traffic metrics. |
| UTM documentation | Manual export now | Request the campaign taxonomy and tagged link documentation before campaign reporting. This is a lightweight document pull, not an integration. |
| Campaign brief | Manual export now | Request the final URL, reporting window, offer list, CTA definitions, active channels, and intended destinations before data pulls are finalized. |
| Email platform | Manual export now if active; not needed if inactive | If Summer Offers email campaigns ran, pull the email campaign report. If email was not active, mark it not needed for this report. |
| Booking engine | Vendor request needed | Completed hotel bookings and revenue require vendor/platform data. Access and integration evidence are not confirmed. |
| SevenRooms | Vendor request needed | Completed dining reservations require SevenRooms data. Access and availability are not confirmed. |
| AXS / Fevo | Vendor request needed | Completed ticket purchases and ticket revenue require AXS / Fevo data. Access and availability are not confirmed. |
| Manual analyst notes / QA | Manual QA now | Document access, export status, event checks, screenshots, and reconciliation notes as the data is gathered. |

Connect later only after the team confirms this reporting need will repeat, the source definitions are stable, ownership is clear, and manual exports show that the data is useful and reconcilable.

## 9. Data Readiness Assessment

Status: Partially Ready

Reason: The approved Summer Offers intake, page performance plan, tracking health audit, campaign reporting plan, and leadership insight summary define the reporting objective, required metrics, expected sources, and caveats. However, no actual source exports, access confirmations, UTM documentation, GTM summaries, Pendo coverage, paid media reports, email reports, or vendor outcome data have been provided yet.

The data map is ready to guide manual pulls and vendor requests, but the report is not ready for performance analysis or leadership conclusions. Vendor-dependent outcomes are not ready until booking engine, SevenRooms, and AXS / Fevo access and exports are confirmed.

## 10. Next Agent to Run

After this Data Source Map is reviewed, collect the manual exports, source access confirmations, GTM QA notes, UTM documentation, and vendor reports listed above.

Then run or rerun the Tracking Health Agent to validate GA4, GTM, UTM, Pendo, platform, and vendor evidence.

After tracking and source evidence are validated, run the Campaign Reporting Agent to produce a final Campaign Performance Report with actual data. Run the Leadership Insight Agent only after validated performance findings and caveats are available.
