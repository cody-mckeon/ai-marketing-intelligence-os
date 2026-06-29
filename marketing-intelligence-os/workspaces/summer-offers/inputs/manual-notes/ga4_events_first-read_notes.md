# GA4 Events First Read Notes

## Source

GA4 Events report filtered or broken down by Landing page + query string for Summer Offers.

## Date Range

March 17, 2026 – June 14, 2026

## Page

/offers/summer and query-string variants

## Event Summary

Top event counts from the export:

- page_view: 388,695
- session_start: 205,917
- first_visit: 245,831
- user_engagement: 123,088
- view_item: 65,772
- book_now_offer_click: 24,072
- scroll: 19,850
- swipe_interactions: 12,790
- file_download: 10,571
- click: 5,522
- genting_rewards_start_signin: 4,492
- view_rooms_click: 4,422
- add_to_cart: 3,204
- begin_checkout: 2,912
- Click_on_file: 2,685
- genting_rewards_start_signup: 728
- purchase: 76
- checkout_continue_shooping: 63
- genting_rewards_signin: 13
- concierge_submission: 1

## Intent and Funnel Signals

The export includes several useful booking or ecommerce-style intent signals:

- book_now_offer_click: 24,072
- view_rooms_click: 4,422
- add_to_cart: 3,204
- begin_checkout: 2,912
- purchase: 76

Using the landing page sessions total of 236,074:

- Book Now offer click rate: approximately 10.2%
- Begin checkout rate: approximately 1.23%
- Purchase rate: approximately 0.03%

These should be treated as preliminary GA4 funnel indicators until event definitions and attribution are validated.

## Revenue Notes

The Events export shows:

- purchase event count: 76
- purchase revenue: $61,573.33

The Landing Page report showed:

- key events: 98
- total revenue: $82,536.19

These numbers do not fully match, so revenue and key event definitions need validation before leadership reporting.

Possible reasons include report filtering differences, key events including more than purchase, landing-page/session attribution behavior, query-string variants, or export limits.

## Caveats

- GA4 event names need definition before final interpretation.
- `purchase` likely represents booking/ecommerce completion, but this must be confirmed.
- Dining reservations and ticket purchases may not be represented in this purchase event.
- `file_download` and `Click_on_file` need investigation.
- Generic `click` events need parameter details before they are useful.
- Query-string variants create many rows and may complicate reporting.
- Revenue should be treated as GA4-attributed revenue requiring validation, not final campaign revenue.