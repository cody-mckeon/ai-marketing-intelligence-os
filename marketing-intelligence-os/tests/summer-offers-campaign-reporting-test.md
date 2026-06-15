# Summer Offers Campaign Reporting Plan Test

## Test Name

Summer Offers Campaign Reporting Plan Test

## Test Prompt

Using the approved Summer Offers Analytics Request Brief, Page Performance Analysis Plan, Leadership Insight Summary, and Tracking Health Audit, create a Campaign Performance Report or Campaign Reporting Plan for the Summer Offers campaign/page.

No actual GA4 export, paid media report, Pendo export, UTM documentation, GTM validation, or vendor conversion data has been provided yet. The Tracking Health Audit status is Not Ready — Missing Data. The output should produce a campaign reporting plan, not a final performance report.

## Expected Output Characteristics

The Campaign Reporting Agent should produce a structured Campaign Performance Report format that functions as a Campaign Reporting Plan because final campaign data and tracking evidence are not available.

The output should use the full Campaign Performance Report format:

- Campaign Summary
- Campaign Goal and Success Criteria
- Audience, Channels, and Traffic Sources
- Landing Page and User Journey
- Performance Metrics
- Campaign Insights
- Data Quality and Tracking Caveats
- Channel and Audience Breakdowns
- Recommended Actions
- Next Agent to Run

The output should clearly state that this is a reporting plan, not a final performance readout.

The output should not claim that the campaign worked, failed, improved, declined, or drove results.

The campaign should be defined as a seasonal offer / campaign landing page initiative for hotel, dining, and entertainment offers.

The business goal should be framed around:

- Qualified traffic
- Offer engagement
- Hotel booking intent
- Dining reservation intent
- Entertainment ticketing intent
- Downstream conversion and revenue visibility, if available from vendor systems

The Performance Metrics section should list required metrics to pull across:

- Delivery metrics
- Traffic metrics
- Engagement metrics
- CTA / intent metrics
- Conversion or revenue metrics, if available

Delivery metrics should include, when relevant:

- Impressions
- Reach
- Spend
- Clicks
- Click-through rate
- Cost per click
- Frequency

Traffic metrics should include:

- Sessions
- Users
- New users
- Landing page sessions
- Source / medium
- Campaign / UTM performance
- Device category

Engagement metrics should include:

- Engaged sessions
- Engagement rate
- Average engagement time
- Page views
- Scroll depth
- Offer card clicks
- Category engagement

CTA / intent metrics should include:

- CTA clicks
- CTA click-through rate
- Book Now clicks
- Check Rates clicks
- Reserve clicks
- Buy Tickets clicks
- Learn More clicks
- Outbound clicks
- Booking intent clicks
- Reservation intent clicks
- Ticket intent clicks
- Form starts

Conversion and revenue metrics should be included only if available and should include:

- Booking completions
- Reservation completions
- Ticket purchases
- Form submissions
- Revenue
- Return on ad spend
- Cost per acquisition
- Conversion rate

The output should separate ad platform delivery metrics from GA4 website traffic metrics.

The output should separate onsite engagement from CTA/intent behavior.

The output should separate onsite intent from completed bookings, reservations, ticket purchases, form submissions, and revenue.

Data quality and tracking caveats should call out the following as missing or unconfirmed:

- UTM documentation
- Paid media reports
- GA4 traffic acquisition data
- GA4 landing page data
- GA4 events data
- Pendo behavior data
- GTM validation
- Vendor conversion data
- Booking engine data
- SevenRooms data
- AXS / Fevo data
- Consent and attribution impacts
- Cross-domain tracking
- Internal traffic filtering
- Platform mismatch between GA4, ad platforms, Pendo, and vendor systems

Recommended actions should include:

- Pull GA4 traffic acquisition, landing page, source / medium, campaign, device, and event data.
- Pull paid media, email, and social campaign reports if those channels were active.
- Confirm UTM naming and campaign documentation.
- Validate GTM tags, triggers, event names, and event parameters for required CTAs.
- Review Pendo behavior data if the Summer Offers page is instrumented there.
- Confirm vendor data availability for booking, reservation, ticketing, form, and revenue outcomes.
- Reconcile GA4, ad platform, Pendo, and vendor reporting windows before producing leadership conclusions.

The next agent or workflow recommendation should be practical, such as:

- Run or rerun the Tracking Health Agent after GA4, GTM, UTM, Pendo, platform, and vendor evidence has been collected.
- Pull and validate campaign data, then rerun the Campaign Reporting Agent for a final Campaign Performance Report.
- Run the Leadership Insight Agent only after validated performance findings are available.

## Acceptance Criteria

- Output uses the full 10-section Campaign Performance Report format.
- Output clearly states that it is a Campaign Reporting Plan because actual data is missing.
- Output does not invent performance results.
- Output does not make leadership performance conclusions while tracking status is Not Ready — Missing Data.
- Output separates delivery, traffic, engagement, CTA/intent, conversion, and revenue metrics.
- Output treats CTA clicks and flow starts as intent unless completed outcomes are confirmed.
- Output includes visible UTM, attribution, tracking, vendor, and platform caveats.
- Output recommends practical data pull and validation steps before final reporting.
