# Entertainment Tracking Health Audit

Status: Partially ready — validated for Entertainment Buy Tickets / Get Tickets intent and vendor handoffs; not ready for event-level, venue-level, artist/show-level, purchase, or revenue attribution.

## 1. Tracking Scope

This audit covers tracking readiness for the Entertainment page:

```text
https://www.rwlasvegas.com/entertainment/
```

The reporting scope includes:

- Entertainment page traffic
- Entertainment detail page traffic
- Event listing engagement
- Filter and view-mode interactions
- Event card clicks
- Buy Tickets / Get Tickets clicks
- Learn More clicks
- Tables clicks
- Vendor handoffs to AXS, Booketing / UrVenue, Zouk Group, and SevenRooms
- Ticketing or reservation intent
- Downstream ticketing purchase attribution, if evidence exists

This audit does not evaluate marketing performance. It only classifies whether the existing evidence can support reporting claims.

## 2. Required Tracking Inventory

The Entertainment reporting workflow should have the following tracking inventory before leadership reporting is treated as complete:

- Page views for `/entertainment/`
- Page views for filtered Entertainment page states, such as category-filtered URLs
- Page views for Entertainment detail pages
- Event listing impressions or visible event count, if available
- Hero carousel clicks
- Event card image clicks
- Event card title clicks
- Buy Tickets clicks
- Get Tickets clicks
- Learn More clicks
- Tables clicks
- Filter interactions:
  - date range
  - category
  - artist search / selector
  - list view
  - agenda view
  - calendar view
- Scroll depth or lazy-load exposure tracking
- Outbound click tracking
- Destination URL
- Destination domain
- Destination vendor
- CTA text
- CTA type
- Entertainment event name
- Venue name
- Artist/show name
- Event date
- Entertainment category
- Ticketing or reservation vendor outcome data, where available
- Purchase or revenue attribution evidence, where available

## 3. Available Tracking Evidence

The following existing evidence was available in the Entertainment workspace and repo operating documents:

- Intake brief: `workspaces/entertainment/inputs/campaign-brief/entertainment-page-intake-brief.md`
- Page inventory: `workspaces/entertainment/inputs/entertainment-page-inventory.md`
- GA4 evidence notes: `workspaces/entertainment/inputs/ga4/entertainment-event-discovery.md`
- GA4 Realtime validation note: `workspaces/entertainment/inputs/ga4/entertainment-buy-tickets-ga4-realtime-validation.md`
- GTM trigger audit: `workspaces/entertainment/inputs/entertainment-buy-tickets-trigger-audit.md`
- GTM validation note: `workspaces/entertainment/inputs/gtm/entertainment-buy-tickets-gtm-validation.md`
- Existing tracking health audit: `workspaces/entertainment/outputs/tracking-health-audit.md`
- Repo guidance: `IDEA.md`, `.hermes.md`, `docs/marketing-intelligence-os-operating-model.md`, and `docs/hermes-agent-ecosystem-map.md`

Confirmed from the available evidence:

- GA4 shows measurable Entertainment page activity, including page views, user engagement, session starts, and first visits.
- GA4 shows traffic to filtered Entertainment states and individual Entertainment detail pages.
- GA4 `click` events are present on Entertainment pages and include `Page title`, `Page location`, `Link URL`, and `Outbound` status.
- Existing GA4 click evidence includes outbound destinations such as `axs.com`, `booketing.com`, and `zoukgrouplv.com`.
- The original GTM trigger named `Entertainment Buy Tickets Button Click` detected Entertainment page clicks using `Click Text contains BUY TICKETS` and `Page Path contains /entertainment`.
- A validated GA4 event tag named `GA4 - Entertainment - Buy Tickets Click` sends event name `entertainment_buy_tickets_click`.
- The validated trigger logic matches `BUY TICKETS` or `GET TICKETS` on Entertainment pages.
- The validated event sends `page_location`, `page_type`, `cta_text`, `cta_type`, `link_url`, `destination_url`, `destination_domain`, `destination_vendor`, and `component_name`.
- Vendor lookup validation passed for AXS, Booketing / UrVenue, Zouk Group, and SevenRooms.
- The GTM validation note says normal left-click testing in GTM Preview successfully triggered the GA4 event and that the tag is ready to publish.
- The GA4 Realtime validation note confirms GA4 Realtime receipt of `entertainment_buy_tickets_click`, with 8 events visible during validation.
- GA4 Realtime displayed event parameters including `page_title`, `page_type`, `destination_domain`, and `destination_vendor`.

Not confirmed from the workspace evidence:

- Standardized Entertainment event name parameter
- Standardized venue name parameter
- Standardized artist/show name parameter
- Standardized event date parameter
- Standardized event category parameter
- Filter interaction events
- Hero carousel click event metadata
- Learn More reporting as a standardized CTA event
- Tables reporting as a standardized CTA event
- GA4 Explore or standard reporting availability for the new `entertainment_buy_tickets_click` event after processing
- Vendor-side ticket purchase data
- Ticketing purchase attribution
- Ticketing revenue attribution

## 4. Readiness Classification by Reporting Claim

| Reporting claim | Readiness status | Evidence basis | Caveats / missing evidence | Next recommended action |
|---|---|---|---|---|
| Entertainment page traffic | Ready | GA4 evidence notes confirm `/entertainment/` has measurable page views, user engagement, session starts, and first visits. | The evidence notes do not include the full export table or reporting date details in this workspace. | Use GA4 page-level reporting with standard date-range caveats. |
| Entertainment detail page traffic | Ready | GA4 evidence notes confirm traffic to individual Entertainment detail pages, including examples such as Ayu Dayclub, Riley Green 2026, and The All-American Rejects. | Detail-page reporting is page-level, not necessarily event-card click attribution. | Report detail-page traffic separately from listing-page CTA intent. |
| Filtered Entertainment page states | Ready with caveats | GA4 evidence notes show filtered states such as `/entertainment/?toid=rw-filters&cat=shows`. | This confirms filtered URLs are visible, not that each filter interaction is captured as a clean event with selected filter metadata. | Use filtered URL reporting directionally; validate explicit filter events before reporting filter interaction rates. |
| Generic outbound click activity | Ready with caveats | GA4 click evidence includes `Link URL` and `Outbound` status for Entertainment pages. | `Link text` is empty in GA4 Explore, so generic click reporting cannot reliably identify CTA text or event metadata. | Use outbound click data only for broad destination analysis unless standardized event metadata is present. |
| Vendor handoffs from generic GA4 click data | Ready with caveats | GA4 click evidence shows outbound destinations including AXS, Booketing, and Zouk Group. | Generic click data lacks clean CTA text, event name, venue, artist/show, and standardized vendor fields. SevenRooms appears in page inventory and GTM validation, but not in the initial GA4 click destination list. | Use generic click data directionally; prefer the validated `entertainment_buy_tickets_click` event for Buy/Get Tickets vendor handoff reporting once available in GA4 reporting. |
| Buy Tickets / Get Tickets CTA intent | Ready with caveats | GTM validation confirms `GA4 - Entertainment - Buy Tickets Click` with event name `entertainment_buy_tickets_click` fired in Preview for normal left-click tests. The GA4 Realtime validation note confirms GA4 Realtime receipt of `entertainment_buy_tickets_click`, with 8 events visible during validation. | Realtime confirms event receipt, but workspace evidence does not yet confirm that the event is fully available in standard GA4 reporting or Explore after processing. The event still lacks standardized event name, venue, artist/show, event date, event category, purchase attribution, and revenue attribution. | Validate the event in GA4 Explore after processing before treating it as standard reporting-ready. |
| Destination vendor handoff by Buy Tickets / Get Tickets CTA | Ready with caveats | GTM validation confirms event parameters for `destination_url`, `destination_domain`, and `destination_vendor`; vendor lookup passed for AXS, Booketing / UrVenue, Zouk Group, and SevenRooms. GA4 Realtime displayed `destination_domain` and `destination_vendor` parameters for `entertainment_buy_tickets_click`. | Realtime confirms vendor-handoff parameter receipt, but workspace evidence does not yet confirm standard GA4 reporting or Explore availability after processing. Vendor lookup values must also stay current as destinations change. | Validate `destination_domain` and `destination_vendor` in GA4 Explore after processing before using them in standard reports. |
| Event-name-level ticketing intent | Not ready | Page inventory identifies event names, but the validated GA4 event does not send standardized event name. | Existing metadata does not support clean reporting by Entertainment event name. | Add a standardized event name parameter to the Entertainment CTA event. |
| Venue-level ticketing intent | Not ready | Page inventory identifies venues, but the validated event does not send standardized venue name. | Existing metadata does not support clean reporting by venue. | Add a standardized venue name parameter to the Entertainment CTA event. |
| Artist/show-level ticketing intent | Not ready | Page inventory identifies artists/shows, but the validated event does not send standardized artist/show name. | Existing metadata does not support clean reporting by artist or show. | Add a standardized artist/show name parameter to the Entertainment CTA event. |
| Event-date-level reporting | Not ready | Page inventory identifies event dates, but the validated event does not send standardized event date. | Existing metadata does not support clean reporting by event date. | Add a standardized event date parameter to the Entertainment CTA event. |
| Entertainment category reporting | Not ready | Page inventory identifies categories such as Shows, Nightclub, Dayclub, dining events, and venue/event types. | The validated event does not send a standardized entertainment category parameter. | Add a standardized entertainment category parameter. |
| Learn More CTA reporting | Not ready | Page inventory confirms Learn More appears on event listings. | Existing validation focused on Buy Tickets / Get Tickets; no standardized Learn More event evidence was provided. | Audit or create a standardized Learn More event only after Buy/Get Tickets reporting is fully validated. |
| Tables CTA reporting | Not ready | Page inventory confirms Tables appears for nightlife/dayclub contexts. | Existing validation focused on Buy Tickets / Get Tickets; no standardized Tables event evidence was provided. | Audit Tables CTA tracking and determine whether it should share the ticketing-intent event or use a separate CTA type. |
| Filter interaction reporting | Not ready | Page inventory documents date, category, artist, and view-mode filters. | No GA4 or GTM evidence confirms filter events or selected filter metadata. | Run a GA4/GTM filter interaction audit. |
| Ticket purchase attribution | Vendor dependency | Intake brief names ticketing attribution as a goal, but no vendor purchase data or GA4 purchase attribution evidence was provided. | Clicks and vendor handoffs are onsite intent only; they do not prove completed ticket purchases. | Request vendor or GA4 ecommerce evidence for ticket purchase events and transaction identifiers. |
| Ticketing revenue attribution | Vendor dependency | No ticketing revenue evidence was provided. | Revenue cannot be inferred from Buy Tickets, Get Tickets, outbound clicks, or vendor handoffs. | Define vendor-side data access and reconciliation requirements before revenue reporting. |

## 5. Safe-to-Report Claims

Based on existing evidence, the following claims are safe or near-safe when worded as tracking readiness rather than performance conclusions:

- GA4 can report Entertainment page traffic.
- GA4 can report Entertainment detail page traffic.
- GA4 can show filtered Entertainment page states when filters create URL states.
- GA4 generic click data can show broad outbound link activity from Entertainment pages.
- Generic outbound click data can identify some destination domains, including AXS, Booketing, and Zouk Group.
- GTM Preview validation supports a standardized Entertainment Buy Tickets / Get Tickets event named `entertainment_buy_tickets_click`.
- GA4 Realtime confirms receipt of `entertainment_buy_tickets_click`, with 8 events visible during validation.
- GA4 Realtime displayed `page_title`, `page_type`, `destination_domain`, and `destination_vendor` parameters for the new event.
- The validated event is designed to support Buy Tickets / Get Tickets intent reporting with CTA text, CTA type, destination URL, destination domain, destination vendor, page location, page type, and component name, but GA4 Explore / standard reporting availability is not yet confirmed in workspace evidence.
- Vendor lookup validation passed for AXS, Booketing / UrVenue, Zouk Group, and SevenRooms.

Recommended wording:

> Entertainment tracking is partially ready. Page-level traffic and detail-page traffic are reportable, and Buy Tickets / Get Tickets intent has now been validated in GTM Preview and confirmed in GA4 Realtime with destination-vendor metadata. Do not treat the new event as GA4 Explore or standard reporting-ready until post-processing evidence confirms it. Reporting should still avoid event-name, venue, artist/show, event-date, purchase, and revenue claims until those fields and downstream outcomes are confirmed.

## 6. Directional-Only Claims

The following can be used directionally, with caveats:

- Generic outbound click volume from Entertainment pages
- Broad destination-domain interest by AXS, Booketing, Zouk Group, and other visible vendors
- Filtered page-state traffic where filter choices appear in the URL
- Detail-page traffic as a proxy for event-detail interest

Caveats:

- Generic GA4 `click` events have empty `Link text` in the reviewed Explore evidence.
- Generic click reporting does not cleanly distinguish Buy Tickets, Get Tickets, Learn More, Tables, event-card clicks, or hero clicks.
- Generic click reporting does not provide standardized event name, venue, artist/show, event date, or event category.
- Directional vendor-domain reporting should not be interpreted as completed ticket sales or revenue.

## 7. Unsupported or Not-Ready Claims

The following claims are not ready based on the current evidence:

- Which specific Entertainment event generated the most ticketing intent
- Which venue generated the most ticketing intent
- Which artist/show generated the most ticketing intent
- Which event date generated the most ticketing intent
- Which Entertainment category generated the most ticketing intent
- How many users clicked Learn More as a standardized CTA
- How many users clicked Tables as a standardized CTA
- Which filters users interacted with most
- Which view mode users used most often
- Whether users interacted with the hero carousel
- Whether Buy Tickets / Get Tickets clicks resulted in purchases
- Whether vendor handoffs resulted in completed ticketing transactions
- Ticketing revenue attribution
- ROAS or revenue performance by Entertainment event, venue, artist/show, or vendor

## 8. Vendor and Platform Dependencies

Downstream outcome reporting depends on vendors and platform integrations.

| Vendor / platform | Current visibility | Dependency |
|---|---|---|
| AXS | Page inventory identifies AXS as a Resorts World Theatre ticketing destination; GA4 click evidence includes `axs.com`; GTM vendor lookup validation passed for AXS. | Purchase attribution requires AXS-side or GA4 ecommerce evidence. |
| Booketing / UrVenue | Page inventory identifies Booketing for Resorts World Live ticketing; GA4 click evidence includes `booketing.com`; GTM vendor lookup validation passed as `urvenue`. | Purchase attribution requires vendor-side or GA4 ecommerce evidence and consistent vendor naming. |
| Zouk Group | Page inventory identifies Zouk Group for Nightclub / Dayclub ticketing and tables; GA4 click evidence includes `zoukgrouplv.com`; GTM vendor lookup validation passed for Zouk Group. | Ticket/table attribution requires Zouk-side or GA4 ecommerce/reservation evidence. |
| SevenRooms | Page inventory identifies SevenRooms for dining event reservations; GTM vendor lookup validation passed for SevenRooms. | Reservation or purchase attribution requires SevenRooms-side evidence or confirmed GA4 event integration. |
| GA4 | GA4 evidence confirms page/detail traffic, generic click metadata, and GA4 Realtime receipt of `entertainment_buy_tickets_click` with `destination_domain` and `destination_vendor` parameters. | Standard reporting still requires post-processing GA4 Explore confirmation in the workspace evidence set. |
| GTM | GTM Preview validation confirms the new event tag and vendor lookup behavior. | Ongoing reporting depends on publish status, no regressions in trigger logic, and keeping destination-vendor lookup values current. |

## 9. Reporting Readiness Assessment

Overall readiness status: **Partially ready**

Reason:

The Entertainment workspace contains enough evidence to support page-level traffic reporting, detail-page traffic reporting, broad outbound-click visibility, and Buy Tickets / Get Tickets intent tracking that is validated in GTM Preview and confirmed in GA4 Realtime. This is a meaningful improvement over generic click tracking because the validated event sends standardized CTA and destination fields, and GA4 Realtime confirms receipt of `destination_domain` and `destination_vendor` parameters.

However, the current evidence does not support clean reporting by Entertainment event name, venue, artist/show, event date, or category. It also does not support ticket purchase attribution or ticketing revenue attribution. Clicks and vendor handoffs must be treated as onsite intent, not completed conversions.

Leadership-safe summary:

> Entertainment tracking is partially ready for traffic, detail-page, and ticketing-intent reporting. Buy Tickets / Get Tickets clicks and vendor handoffs are validated in GTM Preview and confirmed in GA4 Realtime, but should not be treated as GA4 Explore or standard reporting-ready until post-processing evidence confirms availability. Event-level, venue-level, artist/show-level, event-date-level, purchase, and revenue attribution remain not confirmed.

## 10. Recommended Next Actions

Highest-value next action:

- Validate and document the `entertainment_buy_tickets_click` event in GA4 Explore after processing, including whether `destination_domain` and `destination_vendor` are available for standard reporting.

Then prioritize one metadata enhancement:

- Add standardized event context parameters to the Entertainment CTA event:
  - `entertainment_event_name`
  - `venue_name`
  - `artist_show_name`
  - `event_date`
  - `entertainment_category`

Additional follow-up actions:

- Confirm whether GA4 custom dimensions exist for the new event parameters that need to be reported in Explore.
- Audit Learn More and Tables CTA tracking separately from Buy Tickets / Get Tickets.
- Audit filter interaction tracking for date range, category, artist, and view mode.
- Request vendor-side purchase or reservation evidence from AXS, Booketing / UrVenue, Zouk Group, and SevenRooms before claiming completed ticketing, reservations, or revenue.

## Run Summary

### What was updated
- Updated `workspaces/entertainment/outputs/tracking-health-audit.md` only where the new GA4 Realtime validation evidence changed readiness.
- Revised Buy Tickets / Get Tickets CTA intent from Partially ready to Ready with caveats because GA4 Realtime receipt of `entertainment_buy_tickets_click` is now confirmed.
- Revised destination vendor handoff by Buy Tickets / Get Tickets CTA from Partially ready to Ready with caveats because GA4 Realtime displayed `destination_domain` and `destination_vendor` parameters.
- Preserved caveats that GA4 Explore / standard reporting readiness, event name, venue, artist/show, event date, purchase attribution, and revenue attribution are not confirmed.

### Evidence used
- `IDEA.md`
- `.hermes.md`
- `docs/marketing-intelligence-os-operating-model.md`
- `docs/hermes-agent-ecosystem-map.md`
- `workspaces/entertainment/inputs/campaign-brief/entertainment-page-intake-brief.md`
- `workspaces/entertainment/inputs/entertainment-page-inventory.md`
- `workspaces/entertainment/inputs/ga4/entertainment-event-discovery.md`
- `workspaces/entertainment/inputs/ga4/entertainment-buy-tickets-ga4-realtime-validation.md`
- `workspaces/entertainment/inputs/entertainment-buy-tickets-trigger-audit.md`
- `workspaces/entertainment/inputs/gtm/entertainment-buy-tickets-gtm-validation.md`
- Existing `workspaces/entertainment/outputs/tracking-health-audit.md`

### Still missing
- GA4 Explore or standard reporting evidence for `entertainment_buy_tickets_click` after processing.
- Standardized event name, venue name, artist/show name, event date, and entertainment category parameters.
- Learn More, Tables, hero, event-card, and filter interaction validation.
- Vendor-side ticket purchase, reservation, transaction, and revenue evidence.

### Next recommended action
- Validate and document `entertainment_buy_tickets_click` in GA4 Explore after processing, then add standardized event-context parameters for event name, venue, artist/show, event date, and category.

