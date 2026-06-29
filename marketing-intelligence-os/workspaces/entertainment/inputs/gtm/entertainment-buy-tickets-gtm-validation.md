# GTM Validation: Entertainment Buy Tickets Click

## Date Tested

June 2026

## Page Tested

https://www.rwlasvegas.com/entertainment/

## Tag Tested

`GA4 - Entertainment - Buy Tickets Click`

## GA4 Event Name

`entertainment_buy_tickets_click`

## Purpose

Validate a standardized GA4 event for Entertainment Buy Tickets / Get Tickets clicks. The goal is to improve GA4 reporting for ticketing intent, vendor handoffs, and outbound destination analysis from Entertainment pages.

## Trigger Used

`Entertainment Buy Tickets Button Click`

## Trigger Logic

The trigger fires on Entertainment page clicks when:

* `Click Text` matches RegEx `(BUY TICKETS|GET TICKETS)`
* `Page Path` contains `/entertainment`

## Event Parameters Sent

| Parameter            | Value Source / Static Value                   |
| -------------------- | --------------------------------------------- |
| `page_location`      | `{{Page URL}}`                                |
| `page_type`          | `entertainment`                               |
| `cta_text`           | `{{Click Text}}`                              |
| `cta_type`           | `buy_tickets`                                 |
| `link_url`           | `{{Click URL}}`                               |
| `destination_url`    | `{{Click URL}}`                               |
| `destination_domain` | `{{URL - Click URL - Hostname}}`              |
| `destination_vendor` | `{{Lookup - Destination Vendor by Hostname}}` |
| `component_name`     | `entertainment_listing`                       |

## Vendor Lookup Validation

| Test                            | Expected Vendor | Status |
| ------------------------------- | --------------- | ------ |
| AXS / Buy Tickets               | `axs`           | Passed |
| Booketing / Buy Tickets         | `urvenue`       | Passed |
| Zouk Group / Get Tickets        | `zouk_group`    | Passed |
| SevenRooms / Buy or Get Tickets | `sevenrooms`    | Passed |

## Notes

* Right-clicking and choosing “Open Link in New Tab” does not consistently fire the GTM click trigger. This is expected browser behavior and should not be counted as a tracking failure.
* Normal left-click testing in GTM Preview successfully triggered the GA4 event.
* The event currently supports vendor-handoff reporting, CTA intent reporting, page-level reporting, and destination URL analysis.
* The event does not yet capture standardized entertainment event name, venue name, artist name, or event date.

## Validation Result

Passed.

The `GA4 - Entertainment - Buy Tickets Click` tag is ready to publish.
