# Proposed GA4 Evidence Summary — Dining Click / Link URL Discovery

**Workspace:** `workspaces/dining/`  
**GA4 source file:** `workspaces/dining/inputs/ga4/dining-ga4-click-link-url-discovery-20260401-20260629.csv`  
**Report title in export:** `RW Las Vegas - GA4 / Free form-Dining - Click Discovery`  
**Date range:** `20260401-20260629`  
**Agent:** Hermes GA4 Evidence Agent  
**GTM inspected:** No

## Evidence reviewed

GA4 CSV dimensions and metrics available in the export:

| Field | Evidence status |
|---|---|
| `Event name` | Present |
| `Page path + query string` | Present |
| `Link URL` | Present |
| `Link text` | Present as a column, but blank in all data rows |
| `Outbound` | Present |
| `Event count` | Present |
| `Total users` | Present |

Manual inventory context used:

- `workspaces/dining/inputs/manual-notes/dining-page-inventory.md`
- `workspaces/dining/inputs/manual-notes/dining-link-inventory.md`
- `workspaces/dining/inputs/manual-notes/dining-screenshot-index.md`

## Confirmed GA4 findings

### 1. GA4 click events exist on Dining paths

The GA4 export contains only `click` rows.

- Data rows excluding grand total: **3,309**
- Grand total click events: **34,706**
- Grand total users: **21,276**
- Unique `Page path + query string` values: **603**
- Unique base Dining paths: **44**

**Interpretation:** GA4 currently has click-event evidence associated with Dining page paths. This supports Dining outbound click discovery and directional vendor-handoff reporting from GA4.

### 2. `Link URL` is available

The export includes `Link URL`, and the rows contain populated destination URLs.

- Unique Link URLs: **2,270**

**Interpretation:** GA4 can support link-destination analysis for Dining click events in this export. This is useful for identifying outbound vendor handoffs by destination URL/domain.

### 3. `Outbound` is available

The export includes `Outbound`.

- All 3,309 data rows have `Outbound = true`.

**Interpretation:** GA4 can distinguish these exported clicks as outbound clicks. This supports outbound handoff reporting at the event/link level.

**Caveat:** Because every exported row is outbound, this export does not evaluate non-outbound/internal Dining clicks such as `Learn More` clicks to internal Dining detail pages.

### 4. `Link text` is blank

The export includes a `Link text` column, but all data rows are blank.

- Blank `Link text` rows: **3,309 / 3,309**
- Blank `Link text` event count: **34,706 / 34,706**

**Interpretation:** GA4 does **not** currently support CTA-text reporting from this evidence. The export can identify destination URLs/domains, but not reliable CTA labels such as `Reservations`, `Book Now`, or `Learn More`.

## Vendor / outbound handoff findings

### 5. SevenRooms handoff clicks are present

SevenRooms appears in the `Link URL` data.

- SevenRooms click events: **10,423**
- SevenRooms rows: **2,440**
- Unique SevenRooms URLs: **2,166**
- Unique base Dining paths with SevenRooms rows: **20**

Top SevenRooms paths by event count include:

| Page path | Event count |
|---|---:|
| `/dining/` | 1,884 |
| `/dining/alle-lounge-on-66/` | 1,193 |
| `/dining/?toid=tab-fine-dining` | 1,188 |
| `/dining/carversteak/` | 752 |
| `/dining/genting-palace/` | 507 |

**Interpretation:** GA4 supports reporting SevenRooms outbound handoff clicks from Dining paths.

**Reporting boundary:** These are outbound handoff clicks only. They are **not** completed reservations, covers, purchases, or revenue.

### 6. OpenTable handoff clicks are present

OpenTable appears in the `Link URL` data.

- OpenTable click events: **13,694**
- OpenTable rows: **655**
- Unique OpenTable URLs: **28**
- Unique base Dining paths with OpenTable rows: **16**

Top OpenTable paths by event count include:

| Page path | Event count |
|---|---:|
| `/dining/alle-lounge-on-66/` | 1,941 |
| `/dining/` | 1,766 |
| `/dining/?toid=tab-fine-dining` | 1,126 |
| `/dining/genting-palace/` | 827 |
| `/dining/juniors/` | 779 |

**Interpretation:** GA4 supports reporting OpenTable outbound handoff clicks from Dining paths.

**Important inventory note:** The supplied visible-page inventory did not confirm OpenTable outcomes and previously guarded against claiming OpenTable presence/outcomes. This GA4 export does show OpenTable outbound Link URLs on Dining paths, but it still does **not** confirm completed reservations or vendor-side outcomes.

### 7. Grubhub room-service handoff clicks are present

Grubhub appears in the `Link URL` data.

- Grubhub click events: **9,019**
- Grubhub rows: **6**
- Unique Grubhub URLs: **1**
- Base path: `/dining/room-service/`

Top Grubhub path:

| Page path | Event count |
|---|---:|
| `/dining/room-service/` | 7,636 |

**Interpretation:** GA4 supports reporting outbound Grubhub handoff clicks from the Dining room-service path.

**Reporting boundary:** These are outbound handoff clicks only. They are not purchases, orders, revenue, or completed vendor outcomes.

## What this GA4 evidence supports

| Reporting question | GA4 support from this CSV | Caveat |
|---|---|---|
| Dining click events on Dining paths | **Supported** | Export is specific to `click` events and Dining paths. |
| Link URL / destination URL reporting | **Supported** | `Link URL` is populated. |
| Outbound click reporting | **Supported** | `Outbound` is present and all rows are `true`. |
| Vendor handoff reporting by destination domain / URL | **Supported with caveats** | SevenRooms, OpenTable, Grubhub, and other outbound domains are visible. |
| SevenRooms handoff clicks | **Supported** | Clicks only; not completed reservations. |
| OpenTable handoff clicks | **Supported** | Clicks only; not completed reservations. |
| Grubhub room-service handoff clicks | **Supported** | Clicks only; not orders/purchases/revenue. |
| CTA text reporting | **Not supported from this evidence** | `Link text` is blank in every data row. |
| Clean `Reservations` vs `Book Now` CTA-label reporting | **Not supported from this evidence** | Destination URL can imply vendor handoff, but CTA text is unavailable. |
| Internal `Learn More` click reporting | **Not supported by this CSV** | All rows are outbound; internal Dining detail clicks are not evidenced here. |
| Filter interaction reporting | **Not supported by this CSV** | No filter-specific event or filter parameters are present in this export. |
| Completed reservations / covers / purchases / revenue | **Not supported** | No completion, cover, purchase, or revenue evidence is present. |

## Key caveats for Tracking Readiness Agent

1. **Outbound clicks are onsite intent only.**  
   SevenRooms, OpenTable, and Grubhub rows prove outbound handoff click activity, not completed outcomes.

2. **`Link text` is not usable.**  
   The export cannot distinguish CTA labels directly. Reporting can use destination URL/domain, page path, and event count, but not clicked text.

3. **No GTM evidence was reviewed.**  
   This summary does not explain how the click events are implemented, which GTM triggers exist, or whether custom metadata could be added.

4. **No vendor-side evidence was reviewed.**  
   The export does not include SevenRooms, OpenTable, or Grubhub outcome data.

5. **No reservation, cover, purchase, or revenue claims are supported.**  
   The CSV contains click event evidence only.

## Proposed evidence conclusion

GA4 currently supports **Dining outbound click discovery and vendor handoff click reporting** using `Event name`, `Page path + query string`, `Link URL`, `Outbound`, `Event count`, and `Total users`.

GA4 currently supports reporting that users clicked outbound Dining links to vendors including **SevenRooms**, **OpenTable**, and **Grubhub**, with event counts by Dining path and destination URL.

GA4 does **not** currently support, from this evidence alone:

- completed SevenRooms reservations
- completed OpenTable reservations
- Grubhub orders or purchases
- covers
- purchase attribution
- revenue attribution
- CTA text reporting
- clean `Reservations` vs `Book Now` label reporting
- internal `Learn More` click reporting
- Dining filter interaction reporting

## Run Summary

### What was updated
- No files were updated. You asked to review the proposed GA4 evidence summary before writing files.

### Evidence used
- `workspaces/dining/inputs/ga4/dining-ga4-click-link-url-discovery-20260401-20260629.csv`
- `workspaces/dining/inputs/manual-notes/dining-page-inventory.md`
- `workspaces/dining/inputs/manual-notes/dining-link-inventory.md`
- `workspaces/dining/inputs/manual-notes/dining-screenshot-index.md`
- `agents/hermes-ga4-evidence-agent.md`

### Still missing
- GA4 evidence for internal `Learn More` clicks, if available.
- GA4 evidence for filter interactions, if available.
- Any vendor-side evidence for completed reservations, covers, purchases, or revenue. None is present in the supplied CSV.

### Next recommended action
- If this proposed summary looks right, approve a target file path and I can write it as a GA4 evidence note under `workspaces/dining/inputs/ga4/`.
