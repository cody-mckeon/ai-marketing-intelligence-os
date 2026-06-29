# Entertainment Page Inventory Findings

**Page:** https://www.rwlasvegas.com/entertainment/

---

# Page Structure

## Hero / Intro Area

- Hero carousel featuring promoted entertainment
- Large featured artwork
- Entertainment headline:
  - **Cue the Thrills**
- Introductory marketing copy
- Hero slides link to featured event detail pages
- Previous / Next carousel controls

---

## Filters / Navigation

### Date Filter

- Date Range picker
- Start Date
- End Date
- Calendar selector

### Category Filter

- All
- Shows
- Nightclub
- Dayclub

### Artist Filter

Searchable artist list including:

- Resorts World Theatre artists
- Resorts World Live artists
- Zouk Nightclub artists
- Ayu Dayclub artists

### View Modes

- List View
- Agenda View
- Calendar View

---

## Event Listing Structure

Each event card generally contains:

- Event image
- Event name
- Venue
- Event date
- CTA(s)

Typical layouts:

### Resorts World Theatre

- Event image
- Event title
- Venue
- Date
- BUY TICKETS
- Learn More

### Resorts World Live

- Event image
- Event title
- Venue
- Date
- BUY TICKETS
- Learn More

### Nightclub / Dayclub

- Artist image
- Artist name
- Venue
- Date
- Get Tickets
- Tables

### Dining Events

- Event image
- Event title
- Venue
- Date
- BUY TICKETS
- Learn More

---

## Pagination / Loading

Observed behavior:

- Infinite scrolling event list
- Filter-driven updates
- No traditional pagination
- No visible "View More Shows" button
- Likely lazy-loading additional event cards

---

## Other Modules

- Hero carousel
- Entertainment introduction
- Filter controls
- Artist selector
- Calendar selector
- View switcher
- Event listing grid

---

# Event Listings

| Event Name | Venue | Date(s) | Category / Type | CTA Text | Destination URL | Destination Domain | Destination Vendor |
|---|---|---|---|---|---|---|---|
| Ian Asher | Zouk Nightclub | Jun 26 | Nightclub | Get Tickets / Tables | zoukgrouplv.com | zoukgrouplv.com | Zouk Group |
| Mitchell Tenpenny | The Stage at Zouk | Jun 27 | Resorts World Live | Buy Tickets / Learn More | booketing.com | booketing.com | Booketing |
| Saturday Wine Tastings | Wally's | Jun 27 | Dining Event | BUY TICKETS / Learn More | sevenrooms.com | sevenrooms.com | SevenRooms |
| James Hype | Zouk Nightclub | Jun 27 | Nightclub | Get Tickets / Tables | zoukgrouplv.com | zoukgrouplv.com | Zouk Group |
| Meduza | Zouk Nightclub | Jul 3 | Nightclub | Get Tickets / Tables | zoukgrouplv.com | zoukgrouplv.com | Zouk Group |
| Nate Smith | The Stage at Zouk | Jul 4 | Resorts World Live | BUY TICKETS / Learn More | booketing.com | booketing.com | Booketing |
| 4th of July Fireworks Viewing Party | Rose Rooftop | Jul 4 | Special Event | BUY TICKETS / Learn More | zoukgrouplv.com | zoukgrouplv.com | Zouk Group |
| Don Toliver | Zouk Nightclub | Jul 4 | Nightclub | Get Tickets / Tables | zoukgrouplv.com | zoukgrouplv.com | Zouk Group |
| 2 Chainz | Zouk Nightclub | Jul 9 | Nightclub | Get Tickets / Tables | zoukgrouplv.com | zoukgrouplv.com | Zouk Group |
| Martin Lawrence | Resorts World Theatre | Jul 11 | Comedy | BUY TICKETS / Learn More | axs.com | axs.com | AXS |
| Niko Moon | The Stage at Zouk | Jul 18 | Resorts World Live | BUY TICKETS / Learn More | booketing.com | booketing.com | Booketing |
| Ella Mai | Resorts World Theatre | Jul 24 | Concert | BUY TICKETS / Learn More | axs.com | axs.com | AXS |
| The All-American Rejects | Resorts World Theatre | Jul 25 | Concert | BUY TICKETS / Learn More | axs.com | axs.com | AXS |
| Howard Jones | Resorts World Theatre | Jul 26 | Concert | BUY TICKETS / Learn More | axs.com | axs.com | AXS |
| Chris Janson | The Stage at Zouk | Aug 21 | Resorts World Live | BUY TICKETS / Learn More | booketing.com | booketing.com | Booketing |
| Everclear – Lucky 7 Tour with American Hi-Fi | The Stage at Zouk | Aug 22 | Resorts World Live | BUY TICKETS / Learn More | booketing.com | booketing.com | Booketing |

---

# CTAs Found

## Hero

- Hero slide click
- Carousel navigation
- Featured event click

---

## Event CTAs

### Ticket Purchase

- BUY TICKETS
- Get Tickets

### Information

- Learn More

### Nightlife

- Tables

---

## Event Card Interactions

Observed clickable elements:

- Event image
- Event title
- Learn More
- Ticket button
- Tables button

---

## Filter Interactions

Potential interactions include:

- Date Range
- Calendar selection
- Category selection
- Artist selection
- List View
- Agenda View
- Calendar View

---

# Destination Vendor Mapping

| Vendor | Purpose |
|---|---|
| rwlasvegas.com | Event detail pages |
| axs.com | Resorts World Theatre ticketing |
| booketing.com | Resorts World Live ticketing |
| zoukgrouplv.com | Nightclub / Dayclub ticketing & tables |
| sevenrooms.com | Dining event reservations |

## Not Observed

- gofevo.com

Although FEVO exists elsewhere within the Resorts World ecosystem, it does not appear on the Entertainment listing page.

---

# Recommended Tracking Metadata

## Page Context

- page_type
- page_name
- page_path
- page_location

---

## Event Metadata

- event_name
- artist_name
- venue_name
- event_date
- entertainment_category
- event_series

---

## CTA Metadata

- cta_text
- cta_type
- cta_position
- card_position

Suggested CTA types:

- buy_tickets
- get_tickets
- learn_more
- tables
- hero_click

---

## Destination Metadata

- destination_url
- destination_domain
- destination_vendor
- outbound

---

## Filter Metadata

- selected_category
- selected_artist
- selected_date_range
- selected_view
- calendar_month

---

## Interaction Metadata

- filter_used
- hero_slide
- event_card_clicked
- image_vs_button_click
- scroll_depth
- visible_event_count

---

# Initial Tracking Questions

## Event Performance

- Which events receive the most clicks?
- Which artists generate the most engagement?
- Which venues perform best?
- Which event categories perform best?

---

## CTA Performance

- Which CTA performs best?
  - BUY TICKETS
  - Get Tickets
  - Learn More
  - Tables

---

## User Behavior

- How many users interact with the hero?
- Which filters are most frequently used?
- Which artists are searched most often?
- Do users interact with Calendar View?
- How far do users scroll before interacting?
- Do users primarily click images or CTA buttons?

---

## Vendor Performance

- Which outbound vendor receives the most traffic?
- AXS
- Booketing
- Zouk Group
- SevenRooms

---

## Conversion Questions

- Which traffic sources generate the highest ticket-click rate?
- Which events produce the highest outbound CTR?
- Can outbound ticket clicks be tied to downstream purchase events?
- Which entertainment experiences ultimately influence hotel bookings?

---

# Next Deliverable

This inventory provides the structural foundation for the Marketing Intelligence OS.

The next recommended artifact is:

**Entertainment Measurement Plan**

This document should map:

- User interaction
- GTM trigger
- GA4 event
- Required event parameters
- Custom dimensions
- Business question answered

It becomes the implementation blueprint for GTM, GA4, and future Hermes agents responsible for Entertainment reporting.