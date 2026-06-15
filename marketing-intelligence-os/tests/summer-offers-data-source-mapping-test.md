# Summer Offers Data Source Mapping Test

## Test Name

Summer Offers Data Source Mapping Test

## Test Prompt

Using the approved Summer Offers Analytics Request Brief, Page Performance Analysis Plan, Tracking Health Audit, Campaign Reporting Plan, and Leadership Insight Summary, create a Data Source Map for the Summer Offers page/campaign.

No actual GA4 export, Pendo export, GTM tag summary, UTM documentation, paid media report, email report, booking engine report, SevenRooms report, AXS/Fevo report, or vendor conversion data has been provided yet.

The output should map what data sources are needed, what each source can answer, what reports/exports are required, which metrics belong to which source, what caveats apply, and whether each source should be manually exported now or connected later.

## Expected Output Characteristics

The Data Source Mapping Agent should produce the full Data Source Map format:

- Reporting Objective
- Required Data Sources
- Metric-to-Source Map
- Required Exports or Reports
- Required Fields
- Source Ownership and Access
- Caveats by Source
- Manual Export Now vs Connect Later
- Data Readiness Assessment
- Next Agent to Run

The output should not analyze performance or claim that Summer Offers drove traffic, engagement, conversions, reservations, ticket purchases, revenue, improvement, decline, success, or failure.

The reporting objective should be defined around Summer Offers traffic, engagement, campaign performance, CTA/intent behavior, and booking/reservation/ticketing visibility.

The Required Data Sources section should include:

- GA4
- Pendo
- GTM
- Paid media platforms
- UTM documentation
- Booking engine
- SevenRooms
- AXS / Fevo
- Email platform if active
- Campaign brief

The Metric-to-Source Map should:

- Map delivery metrics to paid media, email, or social platforms.
- Map traffic and acquisition metrics to GA4.
- Map onsite engagement to GA4 and Pendo if instrumented.
- Map CTA/intent events to GA4/GTM and Pendo if instrumented.
- Map completed bookings and revenue to the booking engine.
- Map completed dining reservations to SevenRooms.
- Map completed ticket purchases to AXS / Fevo.
- Map UTM taxonomy to UTM documentation and the campaign brief.
- Map tracking validation to GTM and manual QA notes.

The Required Exports or Reports section should list:

- GA4 traffic acquisition report
- GA4 landing page report
- GA4 events report
- Pendo feature/event report
- GTM tag/trigger summary
- Paid media campaign report
- UTM documentation
- Booking engine report
- SevenRooms reservation report
- AXS / Fevo ticketing report
- Email campaign report if active

The Required Fields section should include:

- Date
- Page URL
- Source / medium
- Campaign
- UTM campaign
- UTM content
- UTM term
- Device category
- Event name
- Event count
- CTA label
- Destination URL
- Offer name
- Offer category
- Sessions
- Users
- Engaged sessions
- Engagement rate
- Clicks
- Spend
- Impressions
- Conversions
- Revenue if available

The Source Ownership and Access section should identify likely owners or access points, including:

- Internal website / analytics owner
- Marketing campaign owner
- Paid media agency
- Website agency
- GTM/admin owner
- Pendo admin
- Booking engine vendor
- SevenRooms contact
- AXS / Fevo contact
- Email platform owner
- Agency partner

Unknown ownership should be clearly marked.

The Caveats by Source section should include caveats for:

- GA4
- Pendo
- GTM
- Paid media platforms
- UTM documentation
- Booking engine
- SevenRooms
- AXS / Fevo
- Email platform
- Vendor reports

The Manual Export Now vs Connect Later section should classify each source as Manual export now, Manual QA now, Connect later, Vendor request needed, or Not needed for this report. The output should recommend manual exports first before API or source connections.

The Data Readiness Assessment should provide a readiness status such as Partially Ready, Not Ready — Missing Access, or Not Ready — Vendor Dependency because actual source access and exports are not confirmed.

The Next Agent to Run section should recommend a practical next workflow, such as:

- Run or rerun the Tracking Health Agent after source evidence is collected.
- Run the Campaign Reporting Agent after validated campaign data exists.
- Run the Leadership Insight Agent only after validated performance findings are available.

## Acceptance Criteria

- Output uses the full 10-section Data Source Map format.
- Output does not invent source access or performance results.
- Output clearly maps metrics to source systems.
- Output identifies source-of-truth ownership where possible.
- Output separates manual exports from future connections.
- Output calls out vendor dependencies.
- Output recommends manual data pulls before API integration.
- Output provides a clear data readiness assessment.
- Output recommends a practical next workflow.
