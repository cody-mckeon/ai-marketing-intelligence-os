## Initial GA4 Explore Findings

GA4 confirms that the Entertainment section has measurable traffic and engagement.

The main Entertainment page `/entertainment/` recorded meaningful activity in the last 28 days, including page views, user engagement, session starts, and first visits.

GA4 also records traffic to filtered Entertainment page states, such as `/entertainment/?toid=rw-filters&cat=shows`, and individual Entertainment detail pages, including Ayu Dayclub, Riley Green 2026, and The All-American Rejects.

This confirms that GA4 can support page-level and detail-page-level Entertainment reporting.

However, this initial view does not yet confirm CTA-level tracking, Buy Tickets click tracking, vendor handoff tracking, event-level ticketing intent, or ticketing purchase attribution.

## Link Text Finding

GA4 Explore confirms that Entertainment page `click` events include `Link URL` and `Outbound` status, but `Link text` is empty across rows.

This means the existing `click` event can support outbound destination and vendor-domain analysis, but it cannot reliably distinguish CTA text such as Buy Tickets, Learn More, View More Shows, or event-card clicks.

Current reporting can use `Page title`, `Page location`, and `Link URL` to infer some user intent, but CTA-level and event-level reporting remains limited without standardized metadata.

## Click / Vendor Handoff Discovery

GA4 Explore confirms that `click` events are present on Entertainment pages and include outbound link metadata.

The current `click` event exposes:
- Page title
- Page location
- Link URL
- Outbound status

Visible outbound destinations include:
- `axs.com`
- `booketing.com`
- `zoukgrouplv.com`

This means GA4 can identify that users are clicking from Entertainment pages to external ticketing or event-related vendors.

However, the current Explore view does not yet confirm whether CTA text, event name, venue, category, or clean destination vendor values are captured as standardized reporting fields.