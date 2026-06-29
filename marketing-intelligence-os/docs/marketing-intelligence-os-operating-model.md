# Marketing Intelligence OS Operating Model

## Purpose

The Marketing Intelligence OS exists to help Resorts World Las Vegas marketing reporting become more trustworthy, repeatable, and actionable.

Its job is not only to report performance. Its job is to determine:

* what can be reported confidently
* what should be treated directionally
* what cannot be claimed yet
* what tracking gaps need to be fixed
* what vendor or platform dependencies block attribution

The system prevents leadership reporting from relying on incomplete GA4 data, disconnected vendor tags, or assumptions that are not supported by evidence.

## Core Principle

Marketing reporting must separate performance from measurement readiness.

A page, campaign, or CTA should not be reported as successful or unsuccessful until the system understands whether the underlying tracking can support that claim.

## Operating Workflow

Each page, campaign, or experience should move through the same workflow.

### 1. Intake

Define the business question, page or campaign scope, primary user actions, vendors involved, and expected reporting goals.

Output:

```text
intake-brief.md
```

### 2. Page / Campaign Inventory

Document the visible page structure, content modules, user actions, CTA patterns, destination URLs, vendors, and metadata that should be trackable.

Output:

```text
page-inventory.md
```

### 3. GA4 Evidence Review

Use GA4 Reports, Realtime, DebugView, and Explore to determine what events, dimensions, parameters, traffic, and funnel signals already exist.

Output:

```text
ga4-event-discovery.md
```

### 4. GTM Tracking Audit

Inspect existing GTM tags, triggers, variables, lookup tables, and consent exceptions to determine how current events are firing and what metadata they send.

Output:

```text
gtm-trigger-audit.md
```

### 5. Tracking Readiness Classification

Classify reporting readiness into clear categories:

* Ready
* Ready with caveats
* Partially ready
* Not ready
* Vendor dependency

Output:

```text
tracking-health-audit.md
```

### 6. Fix / Enhancement Recommendation

Identify the highest-value tracking improvement. Prioritize one event or funnel step at a time.

Common examples:

* Book Now click
* Buy Tickets click
* Reserve click
* Learn More click
* file_download
* booking-engine checkout
* ticketing purchase

Output:

```text
tracking-fix-plan.md
```

### 7. GTM / GA4 Validation

Validate changes before and after publish.

Validation sequence:

1. GTM Preview
2. Tag Assistant
3. GA4 DebugView or Realtime
4. GA4 Explore after processing

Output:

```text
gtm-validation.md
```

### 8. Reporting Rules

Define what the data can and cannot support.

Output:

```text
campaign-reporting-plan.md
```

### 9. Leadership Summary

Translate the evidence into executive-ready language.

Output:

```text
leadership-summary.md
```

## Standard Workspace Structure

Each page or campaign should use this structure:

```text
marketing-intelligence-os/
  workspaces/
    [workspace-name]/
      inputs/
        campaign-brief/
        ga4/
        gtm/
        manual-notes/
        paid-media/
        pendo/
        vendors/
      outputs/
        intake-brief.md
        page-performance-plan.md
        tracking-health-audit.md
        campaign-reporting-plan.md
        leadership-summary.md
```

## Readiness Definitions

### Ready

The available data supports the reporting claim with acceptable confidence.

Example:

```text
Entertainment Buy Tickets clicks by destination vendor are reportable.
```

### Ready with Caveats

The data supports directional reporting, but there are known limitations.

Example:

```text
Source / medium reporting is usable, but UTM hygiene issues remain.
```

### Partially Ready

Some funnel steps are validated, but the full reporting claim is not supported.

Example:

```text
Summer Offers rate-code handoffs are validated through booking-engine view_item, but not through checkout or purchase.
```

### Not Ready

The current tracking does not support the reporting claim.

Example:

```text
Offer-level hotel revenue attribution is not ready because rate-code context does not persist into purchase events.
```

### Vendor Dependency

The reporting claim requires tracking changes controlled by a third-party platform or vendor.

Example:

```text
Booking-engine purchase attribution requires rate/package metadata to be passed into GA4 ecommerce events by the booking engine implementation.
```

## Current Validated Use Cases

## Use Case 1: Summer Offers

### Scope

Page:

```text
https://www.rwlasvegas.com/offers/summer/
```

### Validated

* Summer Offers page traffic
* Source / medium traffic mix with caveats
* Enhanced `book_now_offer_click`
* Offer-level Book Now clicks
* Offer-category Book Now clicks
* Rate-code handoffs
* Destination/vendor handoffs
* Booking-engine shop URLs with Summer Offers rate codes
* Booking-engine `view_item` activity by Summer Offers rate code
* Booking-engine `begin_checkout` activity generally

### Remaining Gap

Summer Offers rate-code context appears to drop before checkout. Booking-engine checkout URLs do not preserve:

* `rate`
* `selectedRate`
* `selectedTower`

Hotel booking-engine purchase attribution by Summer Offers rate code is not confirmed.

### Safe to Report

* Offer-level Book Now clicks
* Offer-category Book Now clicks
* Rate-code handoffs
* Destination/vendor handoffs
* Booking-engine `view_item` activity by rate code

### Do Not Claim Yet

* Offer-level checkout starts
* Offer-level hotel purchases
* Offer-level hotel revenue
* Full Summer Offers revenue attribution

## Use Case 2: Entertainment

### Scope

Page:

```text
https://www.rwlasvegas.com/entertainment/
```

### Validated

* Entertainment page traffic
* Entertainment detail page traffic
* Generic click activity
* Outbound link URL visibility
* Published GA4 event: `entertainment_buy_tickets_click`
* Buy Tickets / Get Tickets intent tracking
* Destination vendor handoffs for:

  * AXS
  * UrVenue / Booketing
  * Zouk Group
  * SevenRooms
* GA4 Realtime receipt of the new event

### Remaining Gap

The new Entertainment event does not yet capture standardized:

* entertainment event name
* venue name
* artist/show name
* event date
* event category
* ticket purchase attribution

### Safe to Report

* Entertainment page traffic
* Entertainment detail page traffic
* Entertainment Buy Tickets / Get Tickets clicks
* Destination vendor handoffs
* Outbound ticketing intent by vendor

### Do Not Claim Yet

* Event-name-level ticketing intent
* Venue-level ticketing intent
* Artist/show-level performance
* Event-date-level performance
* Ticket purchase attribution
* Ticketing revenue attribution

## Hermes Agent Ecosystem Direction

The Marketing Intelligence OS should move toward a Hermes-based agent ecosystem.

Hermes should become the execution and orchestration layer for repeatable marketing intelligence workflows.

The human operator still owns judgment, publishing, and final leadership communication.

## Proposed Hermes Agents

### 1. Hermes Marketing Intelligence Orchestrator

Coordinates the workflow for a page, campaign, or tracking audit.

Responsibilities:

* create workspace structure
* select the right agents
* enforce output order
* maintain status
* identify the next action

### 2. Page Inventory Agent

Inspects a page and documents:

* page structure
* content modules
* CTA patterns
* destination URLs
* vendor domains
* visible metadata
* expected tracking fields

### 3. GA4 Evidence Agent

Reviews GA4 evidence and documents:

* traffic
* events
* parameters
* custom dimensions
* Explore findings
* Realtime / DebugView findings
* reporting limitations

### 4. GTM Audit Agent

Reviews GTM tags, triggers, and variables.

Documents:

* tag names
* event names
* trigger logic
* variables used
* parameters sent
* consent exceptions
* implementation risks

### 5. Tracking Readiness Agent

Classifies what is:

* safe to report
* directional only
* not ready
* vendor dependent

### 6. Reporting Rules Agent

Turns evidence into reporting guidance.

Documents:

* metrics to use
* metrics to caveat
* metrics to avoid
* approved reporting language

### 7. Leadership Summary Agent

Creates concise leadership-ready summaries with clear caveats and next steps.

## Hermes Implementation Principle

Do not automate uncertainty.

Hermes should not guess missing tracking context. If the evidence does not support a claim, Hermes should mark it as:

```text
Not confirmed
```

or:

```text
Vendor dependency
```

The system should prefer honest caveats over false confidence.

## Current OS Status

The Marketing Intelligence OS is currently at:

```text
v0.1 - Manual operating model validated with two use cases
```

Validated manual patterns:

* Summer Offers Book Now tracking audit and enhancement
* Entertainment Buy Tickets tracking audit and enhancement

Next milestone:

```text
v0.2 - Package repeatable workflows and define Hermes agent prompts
```

Future milestone:

```text
v0.3 - Hermes-assisted execution for page inventory, GA4 evidence review, GTM audit, tracking readiness, and leadership summary generation
```
