# Summer Offers Intake Test

## Test Name

Summer Offers page leadership-ready performance intake

## Test Prompt

A stakeholder is asking how the Summer Offers page performed. They want something leadership-ready. The page launched in March and includes hotel, dining, and entertainment offers. We need to understand traffic, engagement, CTA clicks, campaign performance, and whether users showed booking intent.

## Expected Output Characteristics

The Marketing Analytics Intake Agent should produce a leadership-ready page/campaign performance brief that clarifies the business question, audience, decision, metrics, data sources, caveats, reporting format, and next agent recommendation before any reporting work begins.

The request type should be classified as Mixed Request because it includes Page Performance, Campaign Performance, Leadership Reporting, Conversion / Intent Analysis, and Vendor / Third-Party Reporting.

The business question should focus on whether the Summer Offers page drove qualified engagement and booking-intent actions.

Recommended metrics should include:

- Sessions
- Users
- Engaged sessions
- Engagement rate
- Traffic source / medium
- UTM campaign performance
- CTA clicks
- Offer/category engagement
- Booking intent clicks
- Reservation clicks
- Ticket clicks
- Scroll depth
- Mobile vs desktop behavior

Likely data sources should include:

- GA4
- Pendo
- GTM
- Booking engine
- SevenRooms
- AXS / Fevo
- Paid media reports
- Campaign UTM documentation

Known caveats should include:

- Third-party booking, reservation, and ticketing platforms may limit full-funnel visibility.
- CTA clicks indicate intent and may not equal completed revenue.
- UTM quality may affect campaign reporting.
- Consent settings may reduce observable tracking.
- GA4 and ad platform numbers may not match.

The suggested reporting format should include:

- Executive summary
- Traffic overview
- Campaign performance
- Offer/category engagement
- CTA and booking-intent behavior
- Device behavior
- Data quality notes
- Recommended next actions

The next agent recommendation should be:

- Page Performance Agent first
- Leadership Insight Agent after the page performance brief is complete

## Acceptance Criteria

- Output uses the full 10-section Analytics Request Brief format.
- Output classifies the request type.
- For the Summer Offers test, output identifies the request as Mixed Request.
- Output lists Page Performance, Campaign Performance, Leadership Reporting, Conversion / Intent Analysis, and Vendor / Third-Party Reporting as included request types.
- Output does not jump directly into final analysis or claim performance results without data.
- Output clearly identifies missing inputs such as exact date range, page URL, campaign names, UTM documentation, CTA/event definitions, and conversion destinations.
- Output separates what can be scoped now from what requires data access, tracking validation, or vendor/platform data.
- Output recommends Page Performance Agent first, then Leadership Insight Agent.
- Output remains concise, practical, and business-oriented.
