# GTM Trigger Audit: Entertainment Buy Tickets Button Click

## Trigger Details

- **Trigger name:** Entertainment Buy Tickets Button Click
- **Trigger type:** Custom Event
- **Fires on:** Some Custom Events
- **Event name:** `click`
- **Conditions:**
  - `Click Text` contains `BUY TICKETS`
  - `Page Path` contains `/entertainment`
- **Exceptions, if any:** None visible

---

## Detection Logic

### Does the trigger rely on Click URL?
No.

### Does the trigger rely on Click Text?
Yes. It only fires when the clicked element's text contains **BUY TICKETS**.

### Does the trigger rely on Page URL or Page Path?
Yes. It uses:

- `Page Path contains /entertainment`

### Which destination domains or URL patterns does it detect?

None.

The trigger does **not** inspect:

- Click URL
- Link URL
- Hostname
- Destination domain
- Vendor URL

### Is this trigger limited to Entertainment pages?

Yes.

It only fires when:

- `Page Path contains /entertainment`

### Could it detect AXS, Booketing, Zouk Group, Fevo, or other ticketing vendors?

No.

It can detect that a **BUY TICKETS** button was clicked on an Entertainment page, but it has no awareness of where the user is going.

Therefore it cannot distinguish between:

- AXS
- Booketing
- FEVO
- Zouk Group
- Internal RWLV pages
- Any future ticket vendor

---

## Reporting Assessment

### Is this trigger reusable for a GA4 Entertainment CTA event?

Yes.

It is a good foundation for a generic **Entertainment CTA Click** event because it identifies the user's intent to purchase tickets.

### What metadata would still be missing?

To support meaningful GA4 reporting, the event should also capture:

- Destination URL
- Destination domain
- Ticket vendor
- Event name
- Venue
- Artist or show
- CTA text (normalized)
- Click URL
- Page URL
- Page title
- Module or card position
- Link classes or element attributes (if needed)

### What risks exist if reused as-is?

- Cannot identify which ticket vendor received the click.
- Cannot distinguish between different events or artists.
- Depends on the visible text being exactly **BUY TICKETS**.
- Will miss buttons with alternate labels (e.g. *Get Tickets*, *Tickets*, *Purchase Tickets*).
- Provides limited insight for downstream GA4 reporting because no contextual metadata accompanies the event.
```