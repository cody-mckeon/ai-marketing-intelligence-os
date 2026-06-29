# GTM Preview Validation: book_now_offer_click

## Date Tested

June 2026

## Page Tested

https://www.rwlasvegas.com/offers/summer/

## Tag Tested

GA4 - Special Offers - Book Now

## Event Name

book_now_offer_click

## Test Summary

The enhanced `book_now_offer_click` tag was tested in GTM Preview mode across the Summer Offers Book Now CTAs.

## Expected Parameters

- cta_text
- cta_type
- link_url
- destination_url
- destination_domain
- destination_vendor
- rate_code
- tower
- offer_name
- offer_category
- component_name

## Test Results

| Offer | Expected Rate Code | Rate Code Passed | Offer Name Passed | Offer Category Passed | Destination Vendor Passed | Status |
|---|---|---|---|---|---|---|
| The Conrad Complete | DSMCD26 |  |  |  |  |  |
| Conrad Pool Package | DCP26 |  |  |  |  |  |
| Warm Days & Bold Flavors | DSPCC26 |  |  |  |  |  |
| Hilton Summer Street Eats | DSPHH26 |  |  |  |  |  |
| Hilton Summer Escape | DSMHH26 |  |  |  |  |  |

## Notes

- GTM successfully detects Book Now clicks using the existing trigger.
- Click URL exposes booking engine URL and rate code.
- Rate code lookup successfully maps Book Now clicks to offer names and offer categories.
- Destination hostname lookup successfully maps reservations.rwlasvegas.com to booking_engine.
- Event is ready for GA4 custom dimension setup if all rows passed.

## Remaining Caveats

- This validates the website handoff event only.
- This does not confirm booking engine arrival tracking, checkout behavior, purchase attribution, or revenue accuracy.
- GA4 custom dimensions still need to be registered before these parameters are usable in standard GA4 reporting.