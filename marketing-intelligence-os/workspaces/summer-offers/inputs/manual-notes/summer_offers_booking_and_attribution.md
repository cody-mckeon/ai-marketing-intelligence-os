# Summer Offers Tracking Finding: Book Now Handoff & Booking Engine Attribution

## Summary

The `book_now_offer_click` event has been enhanced and validated for Summer Offers Book Now CTAs. GTM now captures offer-level metadata at the website handoff point, including offer name, offer category, rate code, CTA type, destination vendor, and component context.

GA4 also confirms that the booking engine subdomain, `reservations.rwlasvegas.com`, is sending activity into the RW Las Vegas GA4 property. Summer Offers rate-code URLs are visible on booking engine shop pages and generate `view_item` activity.

However, rate-code attribution does not appear to persist into the deeper booking funnel. `begin_checkout` events are present on the booking engine, but the checkout page locations do not include `rate`, `selectedRate`, or `selectedTower` values. Hotel booking-engine `purchase` events were not confirmed in the current Explore review.

## What Was Validated

### 1. Website Book Now Click Tracking

The existing GA4 event `book_now_offer_click` fires successfully when users click Book Now CTAs from the Summer Offers page.

Validated parameters include:

| Parameter            | Status    |
| -------------------- | --------- |
| `offer_name`         | Validated |
| `offer_category`     | Validated |
| `rate_code`          | Validated |
| `destination_vendor` | Validated |
| `cta_type`           | Validated |
| `component_name`     | Validated |
| `link_url`           | Validated |
| `destination_url`    | Validated |
| `destination_domain` | Validated |
| `tower`              | Validated |

### 2. Summer Offers Rate Code Mapping

The following Summer Offers rate codes were tested and mapped successfully:

| Rate Code | Offer Name                | Offer Category | Tower  |
| --------- | ------------------------- | -------------- | ------ |
| `DSMCD26` | The Conrad Complete       | hotel          | CONRAD |
| `DCP26`   | Conrad Pool Package       | hotel          | CONRAD |
| `DSPCC26` | Warm Days & Bold Flavors  | dining         | CONRAD |
| `DSPHH26` | Famous Foods Street Feast | dining         | HILTON |
| `DSMHH26` | Hilton Summer Escape      | hotel          | HILTON |

### 3. Booking Engine Visibility in GA4

GA4 Explore confirms that `reservations.rwlasvegas.com` is sending activity into the RW Las Vegas GA4 property.

Confirmed booking engine events include:

| Event            | Hostname                      | Status    |
| ---------------- | ----------------------------- | --------- |
| `page_view`      | `reservations.rwlasvegas.com` | Confirmed |
| `session_start`  | `reservations.rwlasvegas.com` | Confirmed |
| `first_visit`    | `reservations.rwlasvegas.com` | Confirmed |
| `view_item`      | `reservations.rwlasvegas.com` | Confirmed |
| `begin_checkout` | `reservations.rwlasvegas.com` | Confirmed |

### 4. Rate Code Visibility on Booking Engine Shop Pages

Summer Offers rate codes are visible in booking engine shop URLs.

Example:

```text
https://reservations.rwlasvegas.com/ibe/shop.aspx?propertyid=17726&rate=DSMCD26&selectedTower=CONRAD&selectedRate=DSMCD26
```

GA4 Explore confirms that `view_item` events occur on booking engine URLs that include Summer Offers rate codes.

## Key Finding

Summer Offers rate codes are visible at the website click and booking engine shop/view stage, but they do not appear to persist into checkout page locations.

`begin_checkout` events use booking engine URLs such as:

```text
https://reservations.rwlasvegas.com/ibe/combocheckout.aspx?hotelID=17726&lang=en-us&hgID=0&currID=1
```

and:

```text
https://reservations.rwlasvegas.com/ibe/cart.aspx?hotelID=17726&lang=en-us&currID=1
```

These checkout URLs do not include:

```text
rate=
selectedRate=
selectedTower=
```

As a result, GA4 can confirm that users reach the booking engine and that checkout events occur, but it cannot currently attribute checkout starts back to specific Summer Offers rate codes using page location alone.

## What Is Not Yet Confirmed

| Question                                                      | Status                            |
| ------------------------------------------------------------- | --------------------------------- |
| Can GA4 report offer-level Book Now clicks?                   | Yes                               |
| Can GA4 report offer-level booking engine views by rate code? | Yes                               |
| Can GA4 report offer-level checkout starts by rate code?      | Not confirmed                     |
| Can GA4 report offer-level hotel purchases by rate code?      | Not confirmed                     |
| Can GA4 report Summer Offers hotel revenue by offer?          | Not confirmed                     |
| Are hotel booking-engine `purchase` events firing in GA4?     | Not confirmed in this review      |
| Are rate codes available in ecommerce item fields?            | Inconclusive / blocked in Explore |

## Current Reporting Capability

The current setup supports:

* Offer-level Book Now click reporting
* Offer-category click reporting
* Rate-code handoff reporting
* Destination/vendor reporting
* Booking engine shop/view activity by rate code
* Confirmation that booking engine checkout activity exists generally

The current setup does not yet support:

* Offer-level checkout attribution
* Offer-level purchase attribution
* Offer-level revenue attribution
* Confirmed hotel booking purchase reporting by Summer Offers rate code

## Recommended Next Step

Request that the booking engine tracking implementation pass rate/package context into GA4 ecommerce events beyond the shop/view stage.

Needed fields on `begin_checkout` and `purchase` events:

* `rate_code` or `selectedRate`
* `selectedTower`
* offer/package name
* room or rate plan identifier
* transaction ID
* revenue/value on purchase

## Vendor / Internal Follow-Up Question

Can the booking engine pass `rate`, `selectedRate`, and `selectedTower` from the shop URL into GA4 ecommerce events such as `begin_checkout` and `purchase`?

The goal is to preserve Summer Offers attribution from:

```text
Book Now click → booking engine view_item → begin_checkout → purchase
```

## Leadership-Safe Summary

The Summer Offers Book Now handoff is now validated and significantly improved. We can identify which offer was clicked, which rate code was passed, and whether the user reached the booking engine shop/view stage.

The remaining gap is deeper funnel attribution. Booking engine checkout activity is present in GA4, but the checkout URLs do not preserve Summer Offers rate-code context. Until the booking engine passes rate/package metadata into `begin_checkout` and `purchase`, we should not claim offer-level checkout or revenue attribution.
