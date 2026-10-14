# Lieflat Charts Catalog · 63 Charts

> Every chart carries three tags: **data shape** (the primary key for choosing a chart), **occasion**, and **reader time**.
> **Main set and reserve set:** The main set is L1–L15 and F1–F13; charts come from here by default. L16–L20, F14–F17 and G19–G22 are the reserve set. Use them only when the main set cannot encode the data honestly, and state the reason. The exception is the five charts F15, F16, F17, L17 and L20: the main set has no matching encoding for them, so use them directly when the data shape matches (see `SKILL.md`, Section 0, rules 3.1 / 3.2).
> **The selection priority follows the hard rules in `SKILL.md`: by default, audit Lupi Editorial in full first, then Lupi Basics. Go to Glance only when neither group fits, or when the user explicitly asks for Glance / dashboard / three-second read.**
> The "Sibling" column = a pair of charts for the same topic with different structure. It is only for comparing data contracts and recalling candidates. It does not mean both versions should be generated, and it does not change the priority above.
> Reference implementations are in `templates/`: the Glance family in `templates/glance-gallery.html`, the Lupi family in `templates/lupi-gallery.html`, the Basics group in `templates/basics-gallery.html`, maps in `templates/maps-gallery.html`, and large charts in `templates/big-*.html`. Recall maps only when the user explicitly asks for a map or regional distribution. A gallery is a multi-card page: to find the code for a chart, first find the card by the "Card title" in the table below, then search the `<script>` for the `// ════` comment block with the same name. Finished cases with real data are in `examples/`.

## Glance family · 20 charts (thick strokes · pre-aggregated · read in 3 seconds)

| # | Name | Card title | Data shape | Occasion | Reader time | Engine | Sibling |
|---|------|---------|---------|------|---------|------|------|
| G3 | Chunky Bars | Revenue by plan | Ranked comparison of few categories (≤6) | Weekly report, dashboard | <10s | Chart.js* | L2 Dot Cascade; for multiple-choice percentages → L15 Ballot Tally |
| G4 | Dot Waffle | Where sign-ups come from | 100% composition (shares) | General; the default replacement for a pie chart | <10s | Hand-written SVG | L14 Hundred Field |
| G5 | Pictorial Bar | Trees planted, year by year | Yearly counts (one symbol = a fixed quantity) | Public story page | <10s | ECharts | — |
| G6 | Circular Graph (small) | Who works with whom | Network, ≤12 nodes | Quick sketch | <10s | ECharts (dark card) | Preview version of the large chart B1; use B1 for more nodes |
| G7 | Tree LR | Everything the platform ships | Hierarchy (2–3 levels) | Product catalog / architecture page | ~30s | ECharts | — |
| G8 | Rainfall Dual Area | Campaigns rain down | Two-series cause and effect (input vs output) | Growth retrospective | ~30s | ECharts | — |
| G9 | Scatter Morph | One dataset, three views | Carousel of three dimensions of the same entity set | Short video / demo | Animation | ECharts universalTransition | — |
| G10 | Diverging Bar | Where we gained, where we bled | Categorical values with positive and negative | Weekly report, dashboard | <10s | ECharts | — (Equalizer and Meridian Dots were removed) |
| G11 | Force Graph (small) | Integrations, pulled into orbit | Center + satellite network, ≤15 nodes | Quick sketch, draggable | <10s | ECharts (dark card) | Preview version of the large chart B2; static poster version L6 |
| G12 | Stagger Wave | Fifty markets, one wave | Distribution over many categories (30–60 bars) | Short-video intro | Animation | ECharts | — |
| G13 | Big Slice (Custom Pie) | Big slice, deep engagement | Double encoding: share (angle) × intensity (radius) | Product analytics | ~30s | ECharts custom | — |
| G14 | Single Axis | Support load, day by day | Weekday × hour × volume (punch card data) | Support / ops weekly report | ~30s | ECharts | — (Punch Card was removed; this is the only version) |
| G15 | Jitter Strip | Response times, spread out | Distribution by group, individual records (hundreds of points) | SRE / ticket analysis | ~30s | ECharts | — |
| G16 | Bar Race | Eight products race | Rank evolving over time | Short video | Animation | ECharts realtimeSort | — |
| G17 | Dynamic Stream | Concurrent users, streaming | Real-time scrolling series | Live stream / big screen | Animation | ECharts | — |
| G18 | Draw-in + Counter | H1 revenue, drawn in one stroke | Cumulative growth (one line + one big number) | Short video / opening of a briefing | Animation | ECharts | — (Release Rings was removed) |
| G19 | Violin | How fast each plan gets an answer | Density outline of a continuous distribution by group + median | Dashboard / analysis briefing | <10s | SVG | F15 Tick Box; L19 Ridgeline |
| G20 | Matrix Heat (Glance) | Adoption runs hot on the new versions | Two discrete dimensions × value, ≤60 cells, value readable in every cell | Dashboard / product analytics | <10s | SVG | L16 Matrix Heat (close-reading version) |
| G21 | Rank Strip | Flows climbs to the top | Rank of many entities over discrete time, suited to static print | Briefing / bill retrospective | <10s | SVG | G16 Bar Race (dynamic demo) |
| G22 | Aggregate Sankey | Channels pour into plans | Aggregated flow between two ends, band width = quantity, no per-path lookup needed | Attribution / conversion analysis | ~30s | SVG | B3 Threads (per-path lookup) |

\* G1/G3 still use Chart.js; they may later migrate to ECharts to unify the rendering stack.

## Lupi family · 19 charts (hairlines · per record · 30-second read)

| # | Name | Card title | Data shape | Occasion | Reader time | Engine | Sibling |
|---|------|---------|---------|------|---------|------|------|
| L1 | Launch Fan | Twelve features, fanned out | Many entities, each with birth time + current size | Annual report / story page | ~30s | SVG | — |
| L2 | Dot Cascade | What breaks, stacked and ranked | Ranked comparison, countable units (unit chart) | Annual report / story page | ~30s | SVG (dark card) | G3 Chunky Bars |
| L3 | Barcode Lollipop | Ninety days as a barcode | Daily series with one reading per day (90-day scale) | Annual report / story page (with a text column) | ~30s | SVG (full width) |
| L4 | Arc Matrix | Eight products land in twelve cities | Category × category + value, small data (≤100 cells) | Lightweight matrix | ~30s | SVG | Lightweight version of L9 Almanac; use this one when the data is thin |
| L5 | Radial Convergence | 48 requests pull toward five themes | Many-to-one membership, details kept (≤60 items) | Poster / cover | ~30s | SVG | L12 Colonnade (two options to choose from) |
| L6 | Cluster Field | The contributor field | Center + satellite network, poster version | Poster / cover (recognize the form, no lookup) | ~30s | SVG (full width) | B2 force-big (use B2 for interaction / lookup) |
| L7 | Brand Spectrum | Where the brand sits | Bipolar scale (both ends are legitimate positions) + competitor comparison | Brand research report | ~30s | SVG | — (Equalizer was removed; this is the only scale chart kept) |
| L8 | Dotty Matrix | Four squads, stacked in space | Many groups × grid × value, isometric stacking | Cover / poster (strongly decorative) | ~30s | SVG | The flattened G14 is easier to read; use G14 for reading values |
| L9 | Bubble Almanac | Eight years of tickets, one almanac | Category × year + value + status, long span (hand-drawn blob) | Annual report (with side notes / key events) | >30s | SVG (full width) | L4 Arc Matrix (lightweight version) |
| L10 | Radial Patchwork | A quarter of deploys, overlaid | Overlay of individual events: time of day (angle) × size (radius), opacity = density | Annual report / story page | >30s | SVG | — (Polar Line was removed; this is the only 24h distribution chart) |
| L11 | Trend Lineage | Features rise, fall, come back | Lifecycle of an event series (launch / rework / dormant / alive) | Product retrospective | >30s | SVG | — |
| L12 | Type Colonnade | Forty-four repos, ten owners | Many-to-one membership + item-by-item list (≤50 items) | Governance / audit report | ~30s | SVG | L5 Convergence (two options to choose from) |
| L13 | Hourglass Stream | The funnel, poured | Headcount declining stage by stage (funnel) | Annual report / story page | ~30s | SVG | — |
| L14 | Hundred Field | A hundred of us, four minds | 100% composition (shares), small data with ≤6 categories | Annual report / story page | ~30s | SVG | G4 Dot Waffle |
| L15 | Ballot Tally | What they fear, tick by tick | Multiple-choice percentages (each item independently 0–100), ≤6 items | Annual report / story page | ~30s | SVG | G3 Chunky Bars |
| L16 | Matrix Heat | Which features get used together | Two discrete dimensions × value, ≤100 cells, keeps the matrix structure and key cells | Annual report / product analytics | ~30s | SVG | G20 Matrix Heat (quick-read version) |
| L17 | Calendar Heat | A year of deploys, day by day | A full year of dates × value, 52 weeks × 7 days | Annual report / ops retrospective | ~30s | SVG (full width) | F10 Dot Heat (weekday × hour) |
| L19 | Ridgeline | Five pipelines, five tempos | Comparing the density shapes of 3–8 continuous distributions | Annual report / research report | >30s | SVG | G19 Violin (quick read, few groups) |
| L20 | Parallel Coordinates | Twelve products, four dimensions | One entity set across 3–6 continuous dimensions, one line per entity | Product portfolio / research report | >30s | SVG | G9 Scatter Morph (demo carousel) |

> L14–L15 are the **small-data group**: when the data is only a few percentages, unit decomposition brings back Lupi density. 1 dot = 1 person / 1 percentage point, and the density comes from the units, not from the record count. The meaning of the unit must be written in the subtitle (for example "one dot = one person in a hundred"), and only honest units are spread; never invent individuals.

## Basics group · 17 charts (F1–F17 · Lupi grammar × basic chart silhouettes, made for sparse data)

From far away you recognize the basic chart type (bar / line / donut…); up close every unit is countable. This is the first choice in Lupi when the data is only a few categories or a few dozen days. Look here first, and only if nothing fits go to the outside-the-library translation. Reference implementation: `templates/basics-gallery.html`.

| # | Name | Card title | Data shape | Occasion | Reader time | Engine | Sibling |
|---|------|---------|---------|------|---------|------|------|
| F1 | Rung Bars | Revenue by plan, rung by rung | Comparison of few categories (≤8), countable units | Annual report / story page | ~30s | SVG | G3 Chunky Bars |
| F2 | Hairline Line | Thirty days of sign-ups | Daily series (≤30 days, daily readings) | Annual report / story page | ~30s | SVG |
| F3 | Hairline Area | Concurrent users, filled with days | Daily series (30–60 days, reading the shape) | Annual report / story page | ~30s | SVG | L3 Barcode Lollipop |
| F4 | Tick Donut | Where the traffic comes from | 100% composition (≤6 segments) | Annual report / story page | ~30s | SVG | G4 Dot Waffle ⇄ L14 Hundred Field |
| F5 | Tick Rows | Six teams, shipped and counted | Horizontal ranked comparison, countable units (≤8 rows) | Annual report / story page | ~30s | SVG | L2 Dot Cascade |
| F6 | Paired Rungs | This year against last, plan by plan | Grouped comparison (2 series per category, such as then and now) | Annual report / retrospective | ~30s | SVG | — |
| F7 | Stacked Rungs | Where each region's revenue sits | Stacked composition (≤4 categories × ≤3 segments) | Annual report / retrospective | ~30s | SVG | — |
| F8 | Plumb Scatter | Price against satisfaction | Two-dimensional scatter (≤20 points) | Product analytics | ~30s | SVG | G15 Jitter Strip (for distributions) |
| F9 | Rung Waterfall | From gross to net, step by step | Waterfall / increase-decrease decomposition (≤6 steps) | Finance / retrospective | ~30s | SVG | — |
| F10 | Dot Heat | When support gets loud | Weekday × hour × value (small heatmap) | Support / ops | ~30s | SVG | G14 Single Axis |
| F11 | Tick Gauge | How far to the quarter's goal | Single-value progress (0–100%) | Opening of a briefing | <10s | SVG | G18 Draw-in + Counter |
| F12 | Dumbbell Queue | Onboarding, before and after | Category-level before / after comparison (≤6 categories, beads = real units) | Annual report / retrospective | ~30s | SVG | — (the Lupi slot for two-point trends; replaces the removed Slope Beads) |
| F13 | Nested Treemap | Where the work went | Two-level hierarchy + positive weights, rectangle area = value | Budget / product portfolio / space usage | ~30s | ECharts (SVG) | G7 Tree LR (when you only care about membership, not shares) |
| F14 | Rung Histogram | Most tickets resolve within six hours | Binned frequency of a single variable, bins with business meaning and countable units | Support / ops analysis | ~30s | SVG | G19 Violin; F15 Tick Box |
| F15 | Tick Box | Reply times, boxed by plan | Five-number summary + outliers by group, the raw distribution can be summarized | Support / experiment analysis | ~30s | SVG | G19 Violin; F14 Histogram |
| F16 | Stream Ribbon | Three products trade the same river | Composition of 2–5 series over continuous time, with the total in view | Product / traffic retrospective | ~30s | SVG (full width) | F7 Stacked Rungs (static categories) |
| F17 | Candlestick | Six weeks of the token, candle by candle | OHLC four-value time series, hollow = up, solid = down | Market / price retrospective | ~30s | SVG |

## Maps · 2 charts (recalled only when the user explicitly asks for a map)

Country, state/province or region fields in the data **do not mean a map is used automatically**. Choose from `templates/maps-gallery.html` only when the user explicitly asks for a "map", "regional distribution", "color by country/state" and the like. Maps render through ECharts and online GeoJSON, so they need a network connection.

| # | Name | Card title | Data shape | Occasion | Reader time | Engine | Limit |
|---|------|---------|---------|------|---------|------|------|
| M1 | US Choropleth | Sign-ups across the states | US state-level regions + non-negative values, lightness = value | US market / ops report | ~30s | ECharts + GeoJSON | Only when the user explicitly asks; state area does not represent the value |
| M2 | World Choropleth | Where the users are | World country-level regions + non-negative values, lightness = value | Global market / ops report | ~30s | ECharts + GeoJSON | Only when the user explicitly asks; not for points or paths |

## Standalone interactive large charts · 3 charts (one chart per file, full-page size)

| # | File | Data shape | Interaction | When to use |
|---|------|---------|------|-----------|
| B1 | `templates/big-circular.html` | Network, 60 nodes, circular chord membrane | Hover focuses neighbors, click replays | Relationship data with more than 15 nodes |
| B2 | `templates/big-force.html` | Network, 180 nodes, force-directed galaxy | Drag and rebound, hover focus | Large networks where you need to look up individual nodes |
| B3 | `templates/big-threads.html` | Three-segment paths, 100+ threads | Hover a single thread / whole bundle, click to pin, status bar readout | Multi-segment flows where you need to look up individual paths |

## Removed chart types (a better replacement exists)

Polar Line (24h distribution → L10), Punch Card (→ G14), Release Rings (its style belongs to no family), static Thread Triptych (→ B3), Profile Equalizer (→ G10), Slope Beads (crossing slope lines were not readable enough; the slope chart still needs to be redesigned), Meridian Dots (use G10 for positive and negative categories). The last two came from an unused Lenny case draft and are not recommended to restore as they were.
