# Campaign Reporting Plan

## Reporting Rules Based on Tracking Validation

### Safe to Report

The following metrics are currently safe to use for Summer Offers reporting:

- Landing page sessions
- Active users
- New users
- Source / medium traffic mix
- Engagement time
- Bounce rate, with caveats
- Basic event volume
- Offer-level Book Now clicks
- Offer-category Book Now clicks
- Rate-code handoffs to the booking engine
- Destination/vendor handoffs
- Booking-engine `view_item` activity by Summer Offers rate code

### Use Directionally

The following metrics can be used directionally, but should include caveats:

- Key events
- Revenue
- Purchase activity
- Booking-engine checkout activity
- Source / medium performance
- Campaign performance by UTM

### Do Not Claim Yet

The following should not be presented as confirmed until deeper attribution is validated:

- Offer-level checkout starts
- Offer-level hotel purchases
- Offer-level hotel revenue
- Full Summer Offers revenue attribution
- Confirmed Book Now click → checkout → purchase path by offer

### Current Attribution Caveat

GA4 confirms that Summer Offers Book Now clicks now include offer, category, CTA, vendor, and rate-code metadata. GA4 also confirms that Summer Offers rate codes reach the booking-engine shop/view stage.

However, Summer Offers rate-code context does not currently appear to persist into booking-engine checkout URLs, and hotel booking-engine purchase events were not confirmed in the reviewed Explore data.

As a result, reporting should separate:

1. Website engagement and Book Now handoff performance
2. Booking-engine view activity by rate code
3. Checkout/revenue reporting, which remains attribution-limited


