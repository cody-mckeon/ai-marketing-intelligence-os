# Marketing Intelligence OS

## Purpose

This project is the Marketing Intelligence OS for Resorts World Las Vegas marketing analytics, tracking readiness, and leadership reporting.

The system helps determine:

- what marketing performance can be reported confidently
- what should be treated directionally
- what cannot be claimed yet
- what tracking gaps need to be fixed
- what vendor or platform dependencies block attribution

The system should prevent leadership reporting from relying on incomplete GA4 data, disconnected vendor tags, or unsupported attribution assumptions.

## Current Operating Model

Each page, campaign, or experience should follow this workflow:

1. Intake brief
2. Page / campaign inventory
3. GA4 evidence review
4. GTM tracking audit
5. Tracking readiness classification
6. Fix or enhancement recommendation
7. GTM / GA4 validation
8. Reporting rules
9. Leadership summary

## Current Validated Use Cases

### Summer Offers

Workspace:

`workspaces/summer-offers/`

Validated:

- Offer-level Book Now clicks
- Offer-category Book Now clicks
- Rate-code handoffs
- Destination/vendor handoffs
- Booking-engine `view_item` activity by rate code

Known gap:

- Rate-code context does not appear to persist into booking-engine checkout or hotel purchase attribution.

### Entertainment

Workspace:

`workspaces/entertainment/`

Validated:

- Entertainment page traffic
- Entertainment detail page traffic
- Published GA4 event: `entertainment_buy_tickets_click`
- Buy Tickets / Get Tickets intent tracking
- Destination vendor handoffs for AXS, UrVenue/Booketing, Zouk Group, and SevenRooms

Known gap:

- The event does not yet capture standardized event name, venue name, artist/show name, event date, or ticketing purchase attribution.

## Hermes Role

Hermes should act as the execution and orchestration layer for the Marketing Intelligence OS.

Hermes should help run repeatable workflows, update files, summarize evidence, and identify the next action.

Hermes should not guess missing tracking context or overstate attribution.

## Important Guardrails

Hermes should not:

- publish GTM changes
- create GA4 custom dimensions without explicit approval
- infer revenue attribution without evidence
- claim vendor purchase attribution without confirmed event data
- overwrite manual evidence notes without preserving context
- treat generic click volume as clean CTA reporting unless metadata supports it

Hermes should:

- read the repo before acting
- preserve evidence
- document uncertainty
- separate reporting from tracking readiness
- recommend one fix at a time
- require validation before publish
- update outputs only when evidence supports the change

## Key Folders

- `docs/` contains operating model and Hermes ecosystem documentation.
- `agents/` contains agent prompts and role definitions.
- `workspaces/` contains campaign/page-specific work.
- `workspaces/summer-offers/` contains the Summer Offers use case.
- `workspaces/entertainment/` contains the Entertainment use case.

## Near-Term Goal

Move from manual workflow to Hermes-assisted execution.

First Hermes milestone:

Run a controlled workflow where Hermes reads an existing workspace and updates or drafts a tracking health audit using only the evidence files in that workspace.

Hermes should end each run with:

- what was updated
- what evidence was used
- what is still missing
- the next recommended action
