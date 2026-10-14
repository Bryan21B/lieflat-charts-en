# Examples · Finished Cases with Real Data

The galleries in templates/ are "example sentences" (demo data, multiple cards on one page). This folder holds the "finished texts": cases that take the public data of a real article and run the whole skill process, from judging the shape to producing the charts. If you are unsure what a deliverable should look like, look here first.

## r04-financial-report.zh.html

This is a finance-scenario example of the R04 "Monthly Ops" template. It keeps the original text width and the four chart slots, and changes the content into a monthly business financial report: revenue, gross profit, operating cash flow, gross margin, months of runway, daily revenue, collection time windows, revenue composition and gross-profit contribution by business line. The data is fictional demo data, used to show how the same template can fit a finance / economics report.

Preview image: [R04 monthly business financial report](../docs/assets/examples/r04-financial-report.zh.png)

## lenny-2026-survey.html

Data source: Lenny's Newsletter, "How tech workers are feeling in 2026" (2026-07-07, annual survey of tech workers). One article → 8 charts, all in English, with 8 different templates:

This is an early showcase case kept from before the chart-count rule was set, using 8 charts to cover more templates. When the current skill handles a similar article, it filters down to 4–6 charts by default and splits into several pages when there are more than 6.

| # | Template | Data |
|---|------|------|
| 1 | Type Colonnade (L12) | AI identity 49/27/14/5/3 |
| 2 | Ballot Tally (L15) | Triple paradox: enjoy work 79 · significant burnout 56 · optimistic 49 |
| 3 | Hundred Faces (semantic unit · full width) | Layoff worry 28/31/21/12/8, mouth curve = level of worry |
| 4 | Tick Rows (F5) | Four big fears 51/46/41/22 |
| 5 | Hourglass Stream (L13) | Paradox narrows 100 → 77 → 51 |
| 6 | Brand Spectrum (L7) | Segmented NPS −49/−23/−5 |
| 7 | Radial Convergence (L5) | Industry in one word: chaotic 30 / fast 17 / bubble 12 / exciting 11 / other 30 |
| 8 | Ballot Rings (dial ticks · full width) | AI productivity 82 → 49 |

This file also demonstrates a few rules that are easy to forget:

- **Own up to rounding:** after rounding, the identity shares add up to only 98. The footnote says "rounding ate the other two" and does not pad with fake lines.
- **Do not invent data you do not have:** the Brand Spectrum template has competitor comparison points, Lenny has no such data, so they were removed.
- **Turn off random leakage for exact shares:** the rnd leakage logic of the Radial Convergence template (about 8% of items flow to the wrong hub to create an organic feel) must be turned off for survey data.
- **No repeated templates within one batch:** 8 charts, 8 templates.
- **Vertical cascade category names suit only short labels:** this case once used Dot Cascade for the fear data and was judged "hard to read" in two rounds; switching to the horizontal Tick Rows solved it. Keeping labels horizontal is always the safer choice.
- **Do not forget the reduced-motion fallback** (when verifying with a headless screenshot, you can use `--force-prefers-reduced-motion` to bypass the animation timing).
