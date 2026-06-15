# Summer Offers Tracking Health Audit Test

## Test Name

Summer Offers Tracking Health Audit Test

## Test Prompt

Using the approved Summer Offers Analytics Request Brief, Page Performance Analysis Plan, and Leadership Insight Summary, create a Tracking Health Audit for the Summer Offers page.

No actual GA4 export, Pendo export, GTM tag summary, UTM documentation, paid media report, or vendor performance data has been provided yet. The output should assess tracking readiness and identify what must be validated before leadership reporting.

## Expected Output Characteristics

The Tracking Health Agent should produce a structured Tracking Health Audit that assesses whether the Summer Offers page has enough validated tracking evidence to support leadership reporting.

The audit should identify the scope as:

- Summer Offers page
- Hotel, dining, and entertainment offers
- Campaign traffic
- CTA behavior
- Booking, reservation, and ticketing intent

The required tracking inventory should include:

- Page views
- Landing page sessions
- Scroll depth
- Offer card clicks
- Category interactions
- Book Now clicks
- Check Rates clicks
- Reserve clicks
- Buy Tickets clicks
- Learn More clicks
- Outbound/vendor link clicks
- Booking flow starts
- Reservation flow starts
- Ticketing flow starts
- Campaign UTMs
- Device category

The audit should state that available tracking evidence has not yet been provided.

Missing or unconfirmed tracking evidence should include:

- Final page URL
- Reporting date range
- GA4 event names
- GTM triggers
- Pendo coverage
- UTM documentation
- Paid media reports
- Vendor data availability

The audit should not claim that tracking is working without evidence.

The audit should separate onsite intent from completed bookings, reservations, ticket purchases, and revenue.

The audit should call out consent, attribution, cross-domain, internal traffic, reporting window, and platform mismatch caveats.

The audit should assess third-party visibility for:

- Booking engine
- SevenRooms
- AXS
- Fevo

The Reporting Readiness Assessment should use one of these statuses:

- Not Ready - Missing Data
- Not Ready - Validation Needed

Recommended next actions should include:

- Confirm the final URL and reporting date range.
- Pull GA4 event and landing page data.
- Validate GTM tags and triggers for required CTAs and events.
- Check Pendo event or feature coverage.
- Review UTM documentation.
- Collect paid media campaign reports.
- Confirm vendor data access for booking engine, SevenRooms, AXS, and Fevo.

## Acceptance Criteria

- Output uses the full 10-section Tracking Health Audit format.
- Output does not analyze performance.
- Output does not claim events are firing without evidence.
- Output clearly identifies missing validation evidence.
- Output separates onsite intent from completed conversion/revenue.
- Output includes third-party/vendor visibility risks.
- Output gives a clear reporting readiness status.
- Output recommends practical validation steps before leadership reporting.
