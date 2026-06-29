# Dining Page Inventory

Page: https://www.rwlasvegas.com/dining/  
Workspace: `workspaces/dining/`  
Inventory status: Initial visible-page inventory only  
Agent: Hermes Page Inventory Agent  
GA4 audit: Not performed  
GTM audit: Not performed  
Vendor outcome audit: Not performed

## Scope and guardrails

This file documents visible page structure, CTAs, destination URLs, vendor domains, visible metadata, and expected tracking fields for later review.

This inventory does **not** claim or validate:

- GA4 events, GA4 parameters, GA4 custom dimensions, GA4 Explore, Realtime, or DebugView evidence
- GTM tags, GTM triggers, GTM variables, GTM Preview, or Tag Assistant evidence
- SevenRooms completed reservations or vendor-side outcomes
- OpenTable presence or outcomes
- purchases, covers, booking attribution, reservation attribution, or revenue evidence

Visible outbound links are treated only as visible handoff opportunities unless later evidence confirms tracking or downstream outcomes.

## Source context used

Repo / operating context:

- `IDEA.md`
- `.hermes.md`
- `docs/marketing-intelligence-os-operating-model.md`
- `docs/hermes-agent-ecosystem-map.md`
- `agents/hermes-marketing-intelligence-orchestrator.md`
- `agents/hermes-page-inventory-agent.md`
- `workspaces/sitewide-tracking-readiness/outputs/sitewide-tracking-readiness-index.md`

Page context:

- Live visible-page inspection of `https://www.rwlasvegas.com/dining/`

## Visible page metadata

| Field | Visible value |
|---|---|
| Browser/page title | `Explore Dining Options at Resorts World Las Vegas` |
| Canonical URL | `https://www.rwlasvegas.com/dining/` |
| Meta description | `Discover diverse dining options at Resorts World Las Vegas, from fine dining to casual eateries. A taste for every craving!` |
| Robots | `index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1` |
| Open Graph locale | `en_US` |
| Open Graph type | `article` |
| Open Graph title | `Explore Dining Options at Resorts World Las Vegas` |
| Open Graph description | `Discover diverse dining options at Resorts World Las Vegas, from fine dining to casual eateries. A taste for every craving!` |
| Open Graph URL | `https://www.rwlasvegas.com/dining/` |
| Open Graph site name | `Resorts World Las Vegas` |
| Article modified time | `2026-06-15T18:08:34+00:00` |
| Open Graph image | `https://www.rwlasvegas.com/wp-content/uploads/2022/05/famous-foods_wide_1000x880.jpg` |
| Twitter card | `summary_large_image` |

## Visible page structure

### Header / global navigation

Visible header and navigation elements include:

- Accessibility statement link
- Skip to content link
- Resorts World Las Vegas logo / homepage link
- H1: `DINING`
- Sign In
- Resort Calendar
- Guest Services
- Rooms
- Genting Rewards
- Offers
- Pools
- Dining
- Experiences
- Wellness
- Meetings & Events
- Entertainment
- Gaming
- Book Now

### Hero / carousel area

Visible hero elements include:

- Main carousel region
- Previous Slide control
- Next Slide control
- Hero slide image/link examples observed:
  - Wally's
  - Sun's Out Buns Out
  - Famous Foods / Street Feast
  - Vimeo video slide
  - Stubborn Seed
  - Crossroads
  - Kusa Nori
  - Carversteak

### Dining filter area

Visible filter controls include:

- Date & Time / Pick Date-Time
- Category / All Restaurants
- Cuisine / All Cuisine
- Filter Dining
- Remove Filters
- No-results state: `No results for your search criteria`

This inventory does not validate whether filter interactions are tracked or how filter state is represented in analytics.

### Intro module

Visible intro content includes:

- Eyebrow: `DINING`
- H2: `TAKE A WORLDWIDE TOUR OF THE CULINARY ARTS`
- Copy: `With more than 50 food and beverage experiences to explore, Resorts World Las Vegas offers more globally inspired dishes than any other destination on the Strip. Experience our reinvented Room Service powered by Grubhub which puts food and beverage options at your fingertips. From casual market fare to fine dining, we’ve got your cravings covered.`

### Dining listing sections

Visible listing sections include:

- Fine Dining
- Casual Dining
- Famous Foods
- Bars & Lounges
- Quick Eats

## CTA patterns observed

| CTA / interaction type | Visible examples | Notes |
|---|---|---|
| Global hotel booking | `Book Now` | Destination includes `reservations.rwlasvegas.com`; this is a hotel booking-engine handoff, not Dining reservation evidence. |
| Hero carousel interaction | Previous Slide, Next Slide, hero slide clicks | Visible page interaction only; tracking not audited. |
| Hero video controls | Vimeo video slide, audio/pause controls | Visible media interaction only; tracking not audited. |
| Dining filters | Date & Time, Category, Cuisine, Filter Dining, Remove Filters | Filter tracking not audited. |
| Restaurant detail navigation | Restaurant title/card clicks, Learn More | Internal `rwlasvegas.com/dining/...` detail-page navigation. |
| Reservation handoff | `RESERVATIONS` | Visible outbound handoff to `www.sevenrooms.com` for selected venues; completed reservation evidence not reviewed. |
| Footer / utility links | Accessibility, billing, concierge, gift card, location, social links, phone links | Utility navigation outside the Dining content inventory scope. |

## Destination domains observed from Dining content

| Domain | Visible role | Evidence boundary |
|---|---|---|
| `www.rwlasvegas.com` | Internal Dining page, Dining detail pages, navigation, footer links | Visible link/navigation evidence only. |
| `www.sevenrooms.com` | Outbound `RESERVATIONS` handoff links for selected Dining venues | Visible handoff links only; no completed reservation evidence. |
| `reservations.rwlasvegas.com` | Global `Book Now` hotel booking-engine link | Visible global booking link only; not Dining reservation evidence. |
| `rewardsrwlv.joingo.com` | Sign In destination | Visible global navigation only. |
| Vimeo iframe / video embed | Hero carousel video slide | Visible media embed only. |
| Footer/social/utility domains | Hilton, social platforms, Chargerback, Cookiepedia, OneTrust, phone links | Footer/utility links outside primary Dining content. |

No GA4, GTM, SevenRooms-side, OpenTable-side, purchase, reservation, or revenue evidence is inferred from these domains.

## Dining card inventory

The table below lists visible Dining venue cards and their visible destination URLs. A blank reservation field means no visible reservation URL was captured for that card in this pass; it does not prove no reservation path exists elsewhere.

| Section | Visible venue/card text | Internal detail / Learn More URL | Visible reservation URL | Reservation domain |
|---|---|---|---|---|
| Fine Dining | STUBBORN SEED | `https://www.rwlasvegas.com/dining/stubborn-seed/` | `https://www.sevenrooms.com/explore/stubbornseedlv/reservations/create/search/` | `www.sevenrooms.com` |
| Fine Dining | KUSA NORI | `https://www.rwlasvegas.com/dining/kusa-nori/` | `https://www.sevenrooms.com/explore/kusanori/reservations/create/search/` | `www.sevenrooms.com` |
| Fine Dining | WALLY | `https://www.rwlasvegas.com/dining/wallys/` | `https://www.sevenrooms.com/explore/wallysrwlasvegas/reservations/create/search/` | `www.sevenrooms.com` |
| Fine Dining | ¡VIVA! | `https://www.rwlasvegas.com/dining/viva/` | `https://www.sevenrooms.com/explore/vivabyraygarcialasvegas/reservations/create/search/` | `www.sevenrooms.com` |
| Fine Dining | CROSSROADS | `https://www.rwlasvegas.com/dining/crossroads/` | `https://www.sevenrooms.com/explore/rwlvcrossroads/reservations/create/search/` | `www.sevenrooms.com` |
| Fine Dining | GENTING PALACE | `https://www.rwlasvegas.com/dining/genting-palace/` | `https://www.sevenrooms.com/explore/gentingpalace/reservations/create/search/` | `www.sevenrooms.com` |
| Fine Dining | FUHU | `https://www.rwlasvegas.com/dining/fuhu/` | `https://www.sevenrooms.com/explore/fuhu/reservations/create/search/` | `www.sevenrooms.com` |
| Fine Dining | CARVERSTEAK | `https://www.rwlasvegas.com/dining/carversteak/` | `https://www.sevenrooms.com/reservations/carversteak?default_date=2021-12-30` | `www.sevenrooms.com` |
| Fine Dining | BREZZA | `https://www.rwlasvegas.com/dining/brezza/` | `https://www.sevenrooms.com/explore/brezza/reservations/create/search/` | `www.sevenrooms.com` |
| Fine Dining | COPPER SUN | `https://www.rwlasvegas.com/dining/copper-sun/` | `https://www.sevenrooms.com/explore/coppersun/reservations/create/search/` | `www.sevenrooms.com` |
| Casual Dining | AGAVE BAR & GRILL | `https://www.rwlasvegas.com/dining/agave/` |  |  |
| Casual Dining | DAWGHOUSE SALOON | `https://www.rwlasvegas.com/dining/dawg-house-saloon/` | `https://www.sevenrooms.com/explore/dawghousebarandsaloon/reservations/create/search/` | `www.sevenrooms.com` |
| Casual Dining | JUNIOR | `https://www.rwlasvegas.com/dining/juniors/` |  |  |
| Casual Dining | LADY M | `https://www.rwlasvegas.com/dining/lady-m/` |  |  |
| Casual Dining | MULBERRY STREET PIZZERIA | `https://www.rwlasvegas.com/dining/mulberry/` |  |  |
| Casual Dining | Sun’s Out Buns Out | `https://www.rwlasvegas.com/dining/suns-out-buns-out/` |  |  |
| Casual Dining | REDTAIL | `https://www.rwlasvegas.com/dining/redtail/` | `https://www.sevenrooms.com/explore/redtail/reservations/create/search/` | `www.sevenrooms.com` |
| Casual Dining | BITES | `https://www.rwlasvegas.com/dining/bites/` |  |  |
| Famous Foods | Ah Chun Shandong Dumpling | `https://www.rwlasvegas.com/dining/ahchundumpling/` |  |  |
| Famous Foods | HERE KITTY KITTY | `https://www.rwlasvegas.com/dining/herekittykitty/` |  |  |
| Famous Foods | FAMOUS FOODS CENTER BAR | `https://www.rwlasvegas.com/dining/centerbar/` |  |  |
| Famous Foods | FAMOUS PHO | `https://www.rwlasvegas.com/dining/famouspho/` |  |  |
| Famous Foods | FUHU SHACK | `https://www.rwlasvegas.com/dining/fuhushack/` |  |  |
| Famous Foods | GEYLANG CLAYPOT RICE | `https://www.rwlasvegas.com/dining/geylang/` |  |  |
| Famous Foods | HANS FISH & CHIPS | `https://www.rwlasvegas.com/dining/hansfishchips/` |  |  |
| Famous Foods | Harajuku Ramen | `https://www.rwlasvegas.com/dining/harajukuramen/` |  |  |
| Famous Foods | KURU KURU PA | `https://www.rwlasvegas.com/dining/kurukurupa/` |  |  |
| Famous Foods | MICHOS TACOS | `https://www.rwlasvegas.com/dining/michos-tacos/` |  |  |
| Famous Foods | NORI BAR | `https://www.rwlasvegas.com/dining/noribar/` |  |  |
| Famous Foods | SALAD JACK | `https://www.rwlasvegas.com/dining/saladjacks/` |  |  |
| Famous Foods | STREETBIRD | `https://www.rwlasvegas.com/dining/streetbird/` |  |  |
| Famous Foods | SWEET EATS | `https://www.rwlasvegas.com/dining/sweet-eats/` |  |  |
| Famous Foods | TIGER SUGAR | `https://www.rwlasvegas.com/dining/tiger-sugar/` |  |  |
| Famous Foods | WU ZHANG ARTISAN NOODLES | `https://www.rwlasvegas.com/dining/wuzhang/` |  |  |
| Famous Foods | BBQ SMOKE HOUSE | `https://www.rwlasvegas.com/dining/bbq-smoke-house/` |  |  |
| Bars & Lounges | ALLĒ LOUNGE ON 66 | `https://www.rwlasvegas.com/dining/alle-lounge-on-66/` | `https://www.sevenrooms.com/explore/alleloungeon66/reservations/create/search/` | `www.sevenrooms.com` |
| Bars & Lounges | HERE KITTY KITTY | `https://www.rwlasvegas.com/dining/herekittykitty/` |  |  |
| Bars & Lounges | GATSBY | `https://www.rwlasvegas.com/dining/gatsbys-cocktail-lounge/` | `https://www.sevenrooms.com/explore/gatsbyscocktaillounge/reservations/create/search/` | `www.sevenrooms.com` |
| Bars & Lounges | FAMOUS FOODS CENTER BAR | `https://www.rwlasvegas.com/dining/centerbar/` |  |  |
| Bars & Lounges | REDTAIL | `https://www.rwlasvegas.com/dining/redtail/` | `https://www.sevenrooms.com/explore/redtail/reservations/create/search/` | `www.sevenrooms.com` |
| Bars & Lounges | GOLDEN MONKEY TIKI LOUNGE | `https://www.rwlasvegas.com/dining/golden-monkey-tiki-lounge/` |  |  |
| Bars & Lounges | CROSSROADS LOUNGE | `https://www.rwlasvegas.com/dining/crossroads-lounge/` |  |  |
| Bars & Lounges | CROCKFORDS LOBBY BAR | `https://www.rwlasvegas.com/dining/crockfords-lobby-bar/` | `https://www.sevenrooms.com/explore/crockfordslobby/reservations/create/search/` | `www.sevenrooms.com` |
| Bars & Lounges | CONRAD LOBBY BAR | `https://www.rwlasvegas.com/dining/conrad-lobby-bar/` |  |  |
| Bars & Lounges | CRYSTAL BAR | `https://www.rwlasvegas.com/dining/crystal-bar/` |  |  |
| Bars & Lounges | EIGHT CIGAR LOUNGE | `https://www.rwlasvegas.com/dining/eight-cigar-lounge/` | `https://www.sevenrooms.com/explore/eightcigarlounge/reservations/create/search/` | `www.sevenrooms.com` |
| Quick Eats | In-Room Express Dining | `https://www.rwlasvegas.com/dining/room-service/` |  |  |
| Quick Eats | Randy | `https://www.rwlasvegas.com/dining/randys-donuts/` |  |  |
| Quick Eats | STARBUCKS | `https://www.rwlasvegas.com/dining/starbucks/` |  |  |

## Visible SevenRooms handoff links

Visible `RESERVATIONS` links using `www.sevenrooms.com` were captured for selected venues, including:

- Stubborn Seed
- Kusa Nori
- Wally's
- ¡VIVA!
- Crossroads
- Genting Palace
- FUHU
- Carversteak
- Brezza
- Copper Sun
- DawgHouse Saloon
- RedTail
- Allē Lounge on 66
- Gatsby's Cocktail Lounge
- Crockfords Lobby Bar
- Eight Cigar Lounge

RedTail appeared in more than one visible section with the same SevenRooms destination. This is a visible page/content observation only.

## Visible metadata that should be trackable later

Visible page or card attributes that may be useful for later GA4/GTM review include:

- Page family: Dining
- Page URL / canonical URL
- Page title
- Dining section/category, such as Fine Dining, Casual Dining, Famous Foods, Bars & Lounges, Quick Eats
- Venue/card name
- Venue detail URL
- CTA text, such as Reservations or Learn More
- CTA type, such as reservation handoff, internal detail navigation, filter, hero slide, video control, or global booking
- Destination URL
- Destination domain
- Destination vendor label where a visible vendor domain exists
- Filter labels and selected filter values, if selected by the user
- No-results state when filters return no visible matches
- Card order or section position

## Expected tracking fields for later review

These fields are recommended for later measurement design or audit. They are **not confirmed** to exist in GA4, GTM, or any vendor system.

### Page context fields

- `page_family`
- `page_type`
- `page_name`
- `page_title`
- `page_path`
- `page_location`
- `canonical_url`

### Dining venue/card fields

- `dining_venue_name`
- `dining_section`
- `dining_category`
- `dining_cuisine`
- `venue_slug`
- `card_position`
- `section_position`
- `component_name`

### CTA and destination fields

- `cta_text`
- `cta_type`
- `cta_position`
- `click_element`
- `link_url`
- `destination_url`
- `destination_domain`
- `destination_vendor`
- `outbound`

Suggested CTA type values for later review:

- `reservation_handoff`
- `learn_more`
- `venue_card_click`
- `hero_slide_click`
- `filter_apply`
- `filter_remove`
- `global_book_now`
- `video_control`

### Filter fields

- `filter_used`
- `selected_date`
- `selected_time`
- `selected_category`
- `selected_cuisine`
- `filter_result_count`
- `no_results_state`

### Vendor handoff fields

- `reservation_vendor`
- `reservation_destination_url`
- `reservation_destination_domain`
- `restaurant_vendor_slug`

## Screenshot evidence captured

Source: `inputs/manual-notes/dining-screenshot-index.md`

The screenshot index documents visual evidence captured for Dining landing-page states. These screenshots are page-inventory evidence only; they do not confirm GA4 events, GTM tags, completed vendor outcomes, purchases, reservation attribution, or revenue attribution.

| Indexed file | Page state | Inventory note |
|---|---|---|
| `screenshots/01-dining-hero.png` | Hero / top page area | Supports the hero/carousel and top-page structure inventory. |
| `screenshots/02-dining-filter-default.png` | Default filter bar | Supports the default Date & Time, Category, Cuisine, and Filter Dining control inventory. |
| `screenshots/03-dining-fine-dining.png` | Fine Dining section | Supports Fine Dining section/card inventory. Actual workspace file observed as `screenshots/03-fine-dining.png`; filename mismatch should be cleaned up or documented before using screenshot references in downstream outputs. |
| `screenshots/04-dining-casual-dining.png` | Casual Dining section | Supports Casual Dining section/card inventory. |
| `screenshots/05-dining-famous-foods.png` | Famous Foods section | Supports Famous Foods section/card inventory. |
| `screenshots/06-dining-bars-lounges.png` | Bars & Lounges section | Supports Bars & Lounges section/card inventory. |
| `screenshots/07-dining-quick-eats.png` | Quick Eats section | Supports Quick Eats section/card inventory. |
| `screenshots/08-dining-filter-category-open.png` | Category filter open | Supports visible Category filter-state inventory. |
| `screenshots/09-dining-filter-cuisine-open.png` | Cuisine filter open | Supports visible Cuisine filter-state inventory. |
| `screenshots/10-dining-filter-date-time-open.png` | Date/time picker open | Supports visible Date & Time filter-state inventory. |
| `screenshots/11-dining-no-results-state.png` | No-results state | Indexed as capture-if-available; no corresponding file was observed in the current workspace file listing during this update. |

## Fuller link inventory findings

Source: `inputs/manual-notes/dining-link-inventory.md`

The fuller link inventory expands the initial page inventory by separating visible links into global header, hero, filter, section/card, and utility patterns. These are visible link and CTA observations only.

### Link pattern summary

| Pattern | Visible examples | Inventory interpretation |
|---|---|---|
| Global Book Now | Header `Book Now` to `reservations.rwlasvegas.com` | Global hotel booking-engine handoff; not Dining-specific outcome evidence. |
| Hero carousel links / controls | Hero image clicks, Previous Slide, Next Slide | Hero promotional interactions and carousel controls; tracking not audited. |
| Dining filters | Date & Time, Category, Cuisine, Filter Dining | JavaScript-driven visible filter actions; analytics behavior not audited. |
| Internal Dining detail links | Restaurant/card title and `Learn More` links to `/dining/...` detail pages | Internal detail-page navigation; detail-page traffic or click tracking not confirmed. |
| Visible outbound SevenRooms handoff links | Selected `RESERVATIONS` / `Book Now` CTAs with `sevenrooms.com` destinations | Visible outbound handoff links only; no completed reservation or vendor outcome evidence. |
| Informational/internal-only venues | Famous Foods venues and several bars/lounges expose Learn More or informational patterns only in the link inventory | No visible outbound handoff captured for those listed patterns in the link inventory; does not rule out other paths on detail pages. |

### Additional link inventory observations

- The link inventory identifies `rwlasvegas.com`, `sevenrooms.com`, and `reservations.rwlasvegas.com` as the primary visible destination domains for Dining-page content and global booking paths.
- Fine Dining contains the densest set of visible outbound SevenRooms handoff links in the supplied link inventory.
- Casual Dining includes a mix of internal-only cards and selected visible SevenRooms handoff links.
- Famous Foods is documented as following an internal `Learn More` pattern with no visible outbound handoff captured in the supplied link inventory.
- Bars & Lounges includes visible outbound SevenRooms handoff links for selected venues, internal-only venues, and informational-only venues.
- Quick Eats is documented primarily as `Learn More` / internal detail navigation in the supplied link inventory.
- Dining filters are documented as JavaScript-driven rather than URL-driven in the supplied link inventory; this is a page-behavior observation only.
- Carversteak is documented as using a different SevenRooms URL pattern than the other listed SevenRooms handoff links.
- Duplicate `Learn More` links appear on many restaurant cards, which may require separate later audit decisions if reporting needs to distinguish image/title/card clicks from explicit CTA-button clicks.

## Priority CTAs for GA4/GTM audit

The following priorities are recommended for a later GA4/GTM audit. They are not evidence that any GA4 events, GTM tags, triggers, variables, or parameters currently exist.

| Priority | CTA / interaction family | Why it matters for later audit | Expected fields to check later |
|---|---|---|---|
| 1 | Visible SevenRooms handoff CTAs (`RESERVATIONS` / `Book Now` where outbound SevenRooms URLs are present) | Primary visible outbound Dining handoff pattern on selected cards. | `page_family`, `dining_venue_name`, `dining_section`, `cta_text`, `cta_type`, `destination_url`, `destination_domain`, `destination_vendor`, `outbound`, `component_name`, `card_position` |
| 2 | Restaurant `Learn More` / internal detail-page links | Primary internal navigation pattern across all Dining sections. | `page_family`, `dining_venue_name`, `dining_section`, `cta_text`, `cta_type`, `link_url`, `destination_domain`, `component_name`, `card_position` |
| 3 | Hero carousel clicks and controls | Prominent top-page promotional module with image links and carousel controls. | `component_name`, `hero_slide`, `cta_type`, `cta_text`, `destination_url`, `destination_domain`, `slide_position` |
| 4 | Dining filter interactions | Key page-discovery behavior for date/time, category, cuisine, filter apply, and remove-filter states. | `filter_used`, `selected_date`, `selected_time`, `selected_category`, `selected_cuisine`, `filter_result_count`, `no_results_state` |
| 5 | Global `Book Now` CTA | Persistent global conversion-adjacent CTA visible on the Dining page, but not Dining-specific. | `cta_text`, `cta_type`, `destination_url`, `destination_domain`, `page_location`, `component_name` |
| 6 | In-Room Express Dining / Quick Eats internal paths | Distinct Dining content path that may not follow the same outbound handoff pattern as restaurants. | `dining_venue_name`, `dining_section`, `cta_text`, `cta_type`, `link_url`, `component_name` |

Later GA4/GTM audit should verify whether tracking exists and whether the above fields are present. This inventory does not perform that audit.

## Evidence needed next

Before any GA4, GTM, tracking-health, campaign-reporting, or leadership output is created, the next evidence should remain page-inventory evidence only:

1. Screenshot or saved visual evidence of:
   - hero carousel
   - filter bar
   - Fine Dining section
   - Casual Dining section
   - Famous Foods section
   - Bars & Lounges section
   - Quick Eats section
   - no-results state
2. Filter behavior notes:
   - whether filters update the URL
   - whether filters change visible result count
   - whether category/cuisine/date selections persist on reload
3. Dining detail-page spot checks for representative venues:
   - one Fine Dining venue
   - one Casual Dining venue
   - one Famous Foods venue
   - one Bars & Lounges venue
   - one Quick Eats venue
4. Detail-page CTA and metadata inventory:
   - menu links or PDFs, if visible
   - reservation links, if visible
   - phone links, if visible
   - hours/location/cuisine metadata, if visible
   - embedded vendor widgets, if visible

Later agents may request GA4, GTM, or vendor evidence, but that evidence was intentionally not reviewed for this first inventory pass.

## Not confirmed

The following are intentionally not confirmed by this visible-page inventory:

- GA4 event availability
- GA4 event parameters
- GA4 custom dimensions
- GA4 Realtime, DebugView, Explore, or standard reporting availability
- GTM tag names
- GTM trigger logic
- GTM variables
- GTM Preview or Tag Assistant validation
- SevenRooms completed reservations
- OpenTable presence or completed reservations
- purchase attribution
- reservation attribution
- cover counts
- revenue attribution
- dining performance

## Next recommended action

Keep the workflow at the Page Inventory step. The next recommended action is to capture visual evidence and representative Dining detail-page inventory before starting any GA4 Evidence Agent or GTM Audit Agent work.
