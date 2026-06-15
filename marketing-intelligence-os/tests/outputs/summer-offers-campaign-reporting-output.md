# Campaign Performance Report

## 1. Campaign Summary

This is a Campaign Reporting Plan for the Summer Offers campaign/page, not a final Campaign Performance Report. No actual GA4 export, paid media report, Pendo export, UTM documentation, GTM validation, or vendor conversion data has been provided yet, and the Tracking Health Audit status is `Not Ready — Missing Data`.

The Summer Offers initiative should be treated as a seasonal offer / campaign landing page effort launched in March to support hotel, dining, and entertainment offers. The planned reporting should evaluate whether the page and related campaigns attracted qualified traffic, encouraged offer engagement, and created booking, reservation, or ticketing intent.

Because final campaign and tracking data is missing, this report does not claim that the campaign worked, failed, improved, declined, drove conversions, or produced revenue.

## 2. Campaign Goal and Success Criteria

The campaign goal is to help users discover seasonal hotel, dining, and entertainment offers and move toward the appropriate next step: booking, checking rates, reserving, buying tickets, learning more, or entering a vendor flow.

Success should be measured against:

- Qualified traffic to the Summer Offers page
- Engagement with offer content and offer categories
- CTA activity that indicates booking, reservation, ticketing, or offer interest
- Campaign and UTM traffic quality by source, medium, channel, and campaign
- Device-level usability and engagement differences
- Confirmed downstream outcomes only when booking engine, SevenRooms, AXS / Fevo, form, or revenue data is available

CTA clicks, outbound clicks, booking flow starts, reservation flow starts, ticketing flow starts, and form starts should be treated as onsite intent unless completed outcomes are confirmed by downstream systems.

## 3. Audience, Channels, and Traffic Sources

The intended reporting audience is marketing leadership, website/product stakeholders, campaign owners, channel managers, and agency partners.

The intended user audience is visitors interested in seasonal hotel, dining, and entertainment offers.

Channels and traffic sources still need to be confirmed. The reporting plan should account for:

- Paid media traffic, if active
- Email traffic, if active
- Social traffic, if active
- Organic search and direct traffic
- Referral and partner traffic, if relevant
- Source / medium values in GA4
- UTM campaign, content, and term values where available

UTM documentation has not been provided, so campaign source, medium, campaign, creative, content, and term reporting should be considered unconfirmed until taxonomy and link coverage are validated.

## 4. Landing Page and User Journey

The Summer Offers page should be evaluated as an offer/campaign landing page for hotel, dining, and entertainment offers. The final page URL, any landing page variants, and the exact reporting date range still need to be confirmed.

The planned user journey includes:

- Arrive on the Summer Offers page from campaign or non-campaign traffic
- View seasonal offer content
- Scroll to key content areas
- Engage with hotel, dining, or entertainment offer categories
- Click offer cards or offer details
- Click Book Now, Check Rates, Reserve, Buy Tickets, Learn More, or outbound/vendor links
- Move into booking engine, SevenRooms, AXS, Fevo, or another vendor/platform path where applicable

The report should separate onsite engagement and intent from completed bookings, reservations, ticket purchases, form submissions, or revenue.

## 5. Performance Metrics

Because actual campaign data is missing, this section lists the required metrics to pull rather than summarizing performance.

### Delivery Metrics

Pull from paid media, email, social, agency, or platform reports if those channels were active:

- Impressions
- Reach
- Spend
- Clicks
- Click-through rate
- Cost per click
- Frequency

These delivery metrics should not be treated as GA4 website sessions or users. Platform clicks may not match GA4 sessions because of attribution, consent, click/session definitions, bot filtering, and reporting windows.

### Traffic Metrics

Pull from GA4 traffic acquisition, landing page, campaign, and device reports:

- Sessions
- Users
- New users
- Landing page sessions
- Source / medium
- Campaign / UTM performance
- Device category

### Engagement Metrics

Pull from GA4 and Pendo if the Summer Offers page is instrumented there:

- Engaged sessions
- Engagement rate
- Average engagement time
- Page views
- Scroll depth
- Offer card clicks
- Category engagement

Engagement metrics should be reported separately from CTA and downstream conversion behavior.

### CTA / Intent Metrics

Pull from GA4 events, GTM validation, and Pendo if available:

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

These are intent metrics unless downstream platforms confirm completed outcomes.

### Conversion / Revenue Metrics

Include only if available from booking engine, SevenRooms, AXS / Fevo, Ninja Forms, or other vendor/platform reports for the same reporting window:

- Booking completions
- Reservation completions
- Ticket purchases
- Form submissions
- Revenue
- Return on ad spend
- Cost per acquisition
- Conversion rate

Do not infer completed conversion or revenue from onsite CTA clicks or flow starts.

## 6. Campaign Insights

No campaign performance insights can be stated yet because actual GA4, paid media, Pendo, UTM, GTM, and vendor data has not been provided.

Once data is available and validated, this section should evaluate:

- Which channels and source / medium values drove traffic to the page
- Whether campaign traffic appeared qualified based on engagement behavior
- Which hotel, dining, and entertainment offers generated the strongest engagement
- Which CTAs generated booking, reservation, ticketing, or form intent
- Whether mobile and desktop users behaved differently
- Whether downstream vendor data can connect onsite intent to completed bookings, reservations, ticket purchases, form submissions, or revenue
- Where GA4, ad platform, Pendo, and vendor reporting align or diverge

Until then, this section should remain a planned analysis framework and should not be used for leadership performance conclusions.

## 7. Data Quality and Tracking Caveats

The Tracking Health Audit status is `Not Ready — Missing Data`. The following items are missing or unconfirmed:

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
- Final Summer Offers page URL and landing page variants
- Reporting date range
- CTA and event definitions
- Event names and event parameters
- Consent impacts
- Attribution impacts
- Cross-domain tracking
- Internal traffic filtering
- Platform mismatch between GA4, ad platforms, Pendo, and vendor systems

GA4, paid media platforms, Pendo, and vendor systems should be treated as related but not automatically reconcilable. Differences may come from attribution logic, consent behavior, click/session definitions, conversion windows, reporting windows, cross-domain behavior, or vendor visibility limits.

Before this campaign can be used for leadership reporting, the team needs validated evidence across GA4, GTM, campaign UTMs, paid media or other channel platforms, Pendo if applicable, and downstream vendor systems.

## 8. Channel and Audience Breakdowns

Recommended reporting breakdowns include:

- Channel
- Source / medium
- Campaign / UTM campaign
- UTM content or creative
- UTM term, if used
- Paid versus non-paid traffic
- Device category
- New versus returning users
- Audience or geography, if available and relevant
- Hotel, dining, and entertainment offer category
- Individual offer or offer card
- CTA type: Book Now, Check Rates, Reserve, Buy Tickets, Learn More, outbound/vendor link
- Vendor destination: booking engine, SevenRooms, AXS, Fevo, or other destination
- Reporting period, including March launch period versus later campaign activity if relevant

These breakdowns should be used only after UTM taxonomy, campaign documentation, event tracking, and data source coverage are validated.

## 9. Recommended Actions

- Confirm the final Summer Offers page URL, any landing page variants, and the exact reporting date range.
- Pull GA4 traffic acquisition, landing page, source / medium, campaign, device, and event data.
- Pull paid media, email, and social campaign reports if those channels were active.
- Confirm UTM naming, campaign taxonomy, link coverage, and campaign launch documentation.
- Validate GTM tags, triggers, event names, event parameters, destinations, and deduplication for required CTAs and events.
- Review Pendo behavior data if the Summer Offers page is instrumented there.
- Confirm vendor data availability for booking, reservation, ticketing, form, and revenue outcomes.
- Reconcile GA4, ad platform, Pendo, and vendor reporting windows before producing leadership conclusions.
- Keep delivery metrics, GA4 traffic metrics, onsite engagement metrics, CTA/intent metrics, completed conversion metrics, and revenue metrics separated in the final report.
- Produce the final Campaign Performance Report only after the required campaign, tracking, and vendor data has been collected and validated.

## 10. Next Agent to Run

Run or rerun the Tracking Health Agent after GA4, GTM, UTM, Pendo, platform, and vendor evidence has been collected.

After the data is validated, rerun the Campaign Reporting Agent to produce a final Campaign Performance Report with actual findings. Run the Leadership Insight Agent only after validated performance findings and caveats are available.
