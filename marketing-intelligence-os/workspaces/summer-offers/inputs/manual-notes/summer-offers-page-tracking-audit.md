# GA4 / GTM Tracking Audit  
**Page:** `/offers/summer/`  
**Page Title:** `Your Summer Begins at Resorts World | Resorts World Las Vegas`  
**URL:** `https://www.rwlasvegas.com/offers/summer/`

## 1. Offer Inventory

| Offer Name | Category | CTA Text | Destination | Vendor Type | Offer ID / Slug |
|---|---|---|---|---|---|
| The Conrad Complete | Hotel | BOOK NOW | reservations.rwlasvegas.com | Booking Engine | DSMCD26 |
| Conrad Pool Package | Hotel | BOOK NOW | reservations.rwlasvegas.com | Booking Engine | DCP26 |
| Warm Days & Bold Flavors | Dining | BOOK NOW | reservations.rwlasvegas.com | Booking Engine | DSPCC26 |
| Hilton Summer Street Eats | Dining | BOOK NOW | reservations.rwlasvegas.com | Booking Engine | DSPHH26 |
| Hilton Summer Escape | Hotel | BOOK NOW | reservations.rwlasvegas.com | Booking Engine | DSMHH26 |
| Conrad Complete Lunch Menu | Other | Multi-course Lunch Menu | PDF | File Download | Lunch-Conrad-Complete-Menus |
| Conrad Complete Dinner Menu | Other | Multi-course Dinner Menu | PDF | File Download | Dinner-Conrad-Complete-Menus |
| Club 66 | Other | LEARN MORE | /club-66/ | Internal | club-66 |
| Concierge | Other | Learn More | /concierge/ | Internal | concierge |

## 2. CTA Inventory

| CTA Text | Linked URL / Target | Purpose | Destination Vendor | Recommended Event |
|---|---|---|---|---|
| BOOK NOW | reservations.rwlasvegas.com with `rate=DSMCD26` | Start Conrad Complete booking | Booking Engine | `offer_book_now_click` |
| BOOK NOW | reservations.rwlasvegas.com with `rate=DCP26` | Start Conrad Pool Package booking | Booking Engine | `offer_book_now_click` |
| BOOK NOW | reservations.rwlasvegas.com with `rate=DSPCC26` | Start dining package booking | Booking Engine | `offer_book_now_click` |
| BOOK NOW | reservations.rwlasvegas.com with `rate=DSPHH26` | Start Hilton dining package booking | Booking Engine | `offer_book_now_click` |
| BOOK NOW | reservations.rwlasvegas.com with `rate=DSMHH26` | Start Hilton hotel offer booking | Booking Engine | `offer_book_now_click` |
| Check Rates | Booking widget submit | Start general booking search | Booking Engine | `check_rates_click` |
| Multi-course Lunch Menu | PDF | Download/view menu | Internal File | `file_download` |
| Multi-course Dinner Menu | PDF | Download/view menu | Internal File | `file_download` |
| LEARN MORE | /club-66/ | Internal content navigation | Internal | `learn_more_click` |
| Learn More | /concierge/ | Internal content navigation | Internal | `learn_more_click` |

## 3. Recommended Tracking Taxonomy

### Core Events

| Interaction | Recommended Event Name |
|---|---|
| Book Now | `offer_book_now_click` |
| Check Rates | `check_rates_click` |
| Reserve | `reservation_start` |
| Buy Tickets | `ticketing_start` |
| Learn More | `learn_more_click` |
| Offer card click | `offer_card_click` |
| Outbound/vendor link | `outbound_link_click` |
| PDF/file download | `file_download` |
| Booking flow start | `booking_start` |
| Reservation flow start | `reservation_start` |
| Ticketing flow start | `ticketing_start` |

## 4. Required Event Metadata

Every CTA event should send:

| Parameter | Description |
|---|---|
| `page_location` | Full page URL |
| `page_title` | Page title |
| `offer_name` | Human-readable offer name |
| `offer_category` | Hotel, Dining, Entertainment, Other |
| `cta_text` | Visible CTA text |
| `cta_type` | Book Now, Check Rates, Reserve, Buy Tickets, Learn More, File Download |
| `link_url` | Raw clicked URL |
| `destination_url` | Final intended URL |
| `destination_domain` | Destination domain |
| `destination_vendor` | internal, booking_engine, sevenrooms, axs, fevo, file_download, other |
| `rate_code` | Booking rate code, if present |
| `selected_tower` | CONRAD, HILTON, CROCKFORDS, if present |
| `offer_position` | Card/section order |
| `component_name` | Offer Card, Hero, Booking Bar, Nav, Footer |
| `page_type` | Offer Detail / Campaign Landing Page |

## 5. Example Event Payload

```js
dataLayer.push({
  event: "offer_book_now_click",
  page_location: "https://www.rwlasvegas.com/offers/summer/",
  page_title: "Your Summer Begins at Resorts World | Resorts World Las Vegas",
  offer_name: "The Conrad Complete",
  offer_category: "Hotel",
  cta_text: "BOOK NOW",
  cta_type: "book_now",
  link_url: "https://reservations.rwlasvegas.com/ibe/shop.aspx?propertyid=17726&rate=DSMCD26&selectedTower=CONRAD&selectedRate=DSMCD26",
  destination_url: "https://reservations.rwlasvegas.com/ibe/shop.aspx?propertyid=17726&rate=DSMCD26&selectedTower=CONRAD&selectedRate=DSMCD26",
  destination_domain: "reservations.rwlasvegas.com",
  destination_vendor: "booking_engine",
  rate_code: "DSMCD26",
  selected_tower: "CONRAD",
  component_name: "Offer Section",
  page_type: "Campaign Landing Page"
});