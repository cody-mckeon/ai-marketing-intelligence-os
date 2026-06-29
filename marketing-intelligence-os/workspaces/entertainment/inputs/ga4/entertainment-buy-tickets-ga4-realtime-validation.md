# GA4 Realtime Validation: Entertainment Buy Tickets Click

## Date Tested

June 2026

## Page Tested

https://www.rwlasvegas.com/entertainment/

## GA4 Event Validated

`entertainment_buy_tickets_click`

## Validation Source

GA4 Realtime overview.

## Result

GA4 Realtime confirmed receipt of the new event:

`entertainment_buy_tickets_click`

Realtime showed 8 events during validation.

GA4 displayed event parameters including:

- `page_title`
- `page_type`
- `destination_domain`
- `destination_vendor`

## Interpretation

This confirms that the published GTM tag is sending the new Entertainment Buy Tickets / Get Tickets event into the RW Las Vegas GA4 property.

## Caveats

Realtime confirms event receipt, but it does not confirm that the event is fully available in standard GA4 reporting or Explore after processing.

The event still does not capture standardized:

- entertainment event name
- venue name
- artist/show name
- event date
- entertainment category
- ticket purchase attribution
- ticketing revenue attribution

## Validation Status

Passed for GA4 Realtime receipt.