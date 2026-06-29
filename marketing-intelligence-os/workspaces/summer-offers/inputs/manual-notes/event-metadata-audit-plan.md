# Event Metadata Audit Plan

## Purpose

Audit the key GA4 events used for Summer Offers reporting to determine whether they contain enough metadata to support offer-level, CTA-level, destination-level, and conversion-path analysis.

## Current Finding

The `book_now_offer_click` event captures click volume but does not expose enough useful metadata for optimization reporting.

Currently observed parameters:

- batch_ordering_id
- ga_session_id
- ga_session_number
- page_title

Missing useful parameters:

- page_location
- link_url
- link_text
- cta_text
- offer_name
- offer_category
- item_name
- destination_url
- destination_domain
- destination_vendor

## Audit Events

Review the following events:

- book_now_offer_click
- view_rooms_click
- view_item
- add_to_cart
- begin_checkout
- purchase
- scroll
- click
- file_download
- Click_on_file
- Reserve-related events, if present
- Buy Tickets-related events, if present
- Learn More-related events, if present
- Check Rates-related events, if present

## For Each Event, Document

- Event name
- Event count
- Whether it is marked as a key event
- Available parameters
- Missing parameters
- Whether the event supports page-level reporting
- Whether the event supports offer-level reporting
- Whether the event supports CTA-level reporting
- Whether the event supports destination/vendor reporting
- Whether the event supports conversion/revenue attribution
- Recommended fix
- Priority level: Critical, High, Medium, Low

## Minimum Recommended Parameters for CTA Events

- page_location
- page_title
- event_name
- cta_text
- cta_type
- offer_name
- offer_category
- link_url
- destination_url
- destination_domain
- destination_vendor

## Minimum Recommended Parameters for Ecommerce/Funnel Events

- page_location
- item_name
- item_category
- offer_name
- offer_category
- funnel_step
- booking_engine
- transaction_id, if privacy-approved and available
- value, if available
- currency, if available

## Priority Events

Critical:
- purchase
- begin_checkout
- add_to_cart

High:
- book_now_offer_click
- view_rooms_click
- Reserve clicks
- Buy Tickets clicks
- Check Rates clicks

Medium:
- Learn More clicks
- file_download
- Click_on_file
- generic click

## Reporting Rule

Events with weak metadata can be used for directional volume reporting only.

Events should not be used for offer-level, CTA-level, destination-level, or optimization reporting unless the required parameters are present and validated.