# Summer Offers Leadership Insight Framework Test

## Test Name

Summer Offers Leadership Insight Framework Test

## Test Prompt

Using the approved Summer Offers Analytics Request Brief and Page Performance Analysis Plan, create a Leadership Insight Summary for the Summer Offers page.

No actual GA4, Pendo, paid media, or vendor performance data has been provided yet. The output should create a leadership-ready narrative framework, not claim actual results.

## Expected Output Characteristics

The Leadership Insight Agent should produce a structured Leadership Insight Summary that translates the approved brief and page performance plan into a concise leadership narrative framework.

The output should use the full Leadership Insight Summary format:

- Executive Summary
- What We Measured
- What Changed or Happened
- Why It Matters
- Key Signals
- Data Caveats
- Recommended Actions
- Leadership-Ready Language
- Open Questions
- Next Agent to Run

The output should not claim that performance improved, declined, succeeded, or failed.

The leadership story should be framed around:

- Traffic quality
- Qualified engagement
- Campaign performance
- Offer/category engagement across hotel, dining, and entertainment offers
- CTA intent
- Booking, reservation, and ticketing flow starts
- Mobile versus desktop behavior
- Third-party conversion visibility
- Data trust and tracking health

CTA clicks, outbound clicks, booking flow starts, reservation flow starts, and ticketing flow starts should be explained as intent signals, not completed bookings, reservations, ticket purchases, or revenue.

Data caveats should be visible and should include:

- Missing final GA4 performance data
- Missing Pendo behavior data
- Missing paid media performance data
- Missing or unconfirmed UTM documentation
- Missing or unconfirmed GTM event validation
- Unconfirmed booking engine, SevenRooms, and AXS / Fevo data availability
- Potential third-party platform visibility gaps
- Attribution differences between GA4, paid media platforms, and vendor systems

Recommended next actions should include:

- Pull GA4 page, engagement, event, source / medium, campaign, and device data
- Validate GTM event firing and event names
- Review Pendo behavior if the Summer Offers page is instrumented there
- Collect UTM documentation and campaign launch context
- Confirm vendor data availability for booking, reservation, and ticketing outcomes
- Separate intent metrics from completed conversion or revenue metrics

The output should provide usable leadership-ready language that is careful and caveated because final performance data is not yet available.

The next agent or workflow recommendation should be practical, such as:

- Pull and validate analytics exports, then rerun Leadership Insight Agent with actual findings
- Run a final page performance analysis workflow before publishing the leadership readout

## Acceptance Criteria

- Output uses the full 10-section Leadership Insight Summary format.
- Output does not invent results.
- Output separates narrative framework from actual findings.
- Output includes clear caveats around third-party platforms and intent versus completed conversion.
- Output provides a leadership-ready paragraph that can be used safely before final data is available.
- Output recommends the next practical workflow or agent.
