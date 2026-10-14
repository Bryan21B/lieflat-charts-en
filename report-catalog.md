# Lieflat Charts Report Template Catalog · 12 Templates

> A report template decides the narrative order, text width, module density and reading speed of the whole page. The charts inside the page must still follow the data contract in `catalog.md`. The scenarios in the table below are recommended uses, not hard limits: the same layout can carry finance and economics, research, business, product and personal records.
> Every template comes in two independent versions, Chinese and English: `templates/reports/report-NN.zh.html` and `templates/reports/report-NN.en.html`.
> The visual index is in `templates/reports/index.html`, and the static previews are in `docs/assets/reports/`.

## Selection order

1. First filter by report type, audience and reading task. Do not filter by "which chart is inside" or by the industry word in the template name.
2. Then filter by information density, text width, reading speed and whether it must run offline.
3. Compare at least 3 candidates; when there are fewer than 3, compare all of them.
4. Once you lock one report template, keep its whole-page skeleton and do not splice blocks from other report templates.

## Template index

| # | Chinese name / English | Common report types / transferable scenarios | Text width | Density | Color system | Dependencies |
|---|---|---|---:|---|---|---|
| R01 | 调研一页纸 / Survey One-Pager | Survey report, research brief, policy / market insight, opening of a white paper, public data release | 1080 | 3 charts, medium | Porcelain | Web fonts (network) |
| R02 | 年度里程碑 / Annual Milestones | Annual review, results / financial-report recap, investor update, product or project milestones | 980 | 3 charts, medium | Palm | Web fonts (network) |
| R03 | 年度数据海报 / Year in Data | Annual data report, business / financial annual report, personal year record, annual trend poster | 1080 | 4 charts, fairly high | Wire | Web fonts (network) |
| R04 | 月度运营 / Monthly Ops | Monthly report, business data report, financial report, ops / finance review, periodic monitoring | 1080 | 4 charts, fairly high | Porcelain | Web fonts (network) |
| R05 | 影响力故事 / Impact Story | Project retrospective, product record, public-interest / community case, impact narrative, personal growth record | 760 | 2 charts, low | Mono | Web fonts (network) |
| R06 | 产品八年年鉴 / Eight-Year Product Almanac | Long-span almanac, product / company history, multi-year financial or business trends, long-term personal data | 980 | 4 charts, high | Palm | Web fonts (network) |
| R07 | 调研拼贴海报 / Survey Collage Poster | Survey report poster, user / market research, event / expo data, social media material | 980 | 5 charts, very high | Palm | Web fonts (network) |
| R08 | 单位人群一页 / Population One-Pager | Population / user persona, policy / public-interest brief, market segmentation, demographic and socioeconomic data | 880 | 2 charts, low | Wire | Web fonts (network) |
| R09 | 数据故事仪表盘 / Data Story Dashboard | Dashboard, finance / business cockpit, business overview, competitor / market comparison, KPI snapshot | 1080 | 4 charts + KPIs, high | Porcelain | Web fonts (network) |
| R10 | 旅行手记 / Travel Notebook | Travel data record, sports data record, personal annual / life data, lightweight project log | 980 | 4 charts + table, medium | Palm | Web fonts (network) |
| R11 | 研究简报卡 / Research Brief Card | Research brief, finance / economics flash, social media card, briefing insert, key-metric snapshot | 600×1000 | 2 charts, fixed size | Mono | Chart.js + ECharts CDN |
| R12 | 周报速览 / Weekly Glance | Weekly report, finance / business flash, ops monitoring, project progress, sports or travel weekly diary | 1080 | 4 charts, high | Palm | Chart.js + ECharts CDN |

## Recall by report type

- **Survey report / research brief:** R01, R07, R08, R11.
- **Business data report / dashboard:** R04, R09, R12.
- **Financial report / finance and economics report:** R02, R03, R04, R09, R11, R12. A finance version of R04 is in `examples/reports/r04-financial-report.zh.html`.
- **Product record / project retrospective:** R02, R05, R06, R12.
- **Personal data record:** R03, R05, R06, R10, R12; sports, travel and annual life data can all use these.
- **Public poster / social media sharing:** R03, R07, R11.
- **Template selection principle:** choose by content structure, information density, reading speed and text width. Do not restrict a template to one industry just because its name says "travel", "operations" or "almanac".
- **Must run offline:** prefer R01–R10 and inline or remove the web fonts; R11–R12 also need their chart dependencies inlined.
- **Fixed social media frame:** R11; if the content does not fit, switch templates, and do not shrink the font or crop information.

## Template contract

- A report template is a complete page, not a chart gallery. Copy the whole HTML of the matching language as the starting point.
- Keep the template's text width, main grid, section order, main whitespace, color system and the relationships between chart slots.
- You may replace the copy, data, sources, legends and any module that conflicts with the real content; you may delete secondary modules that have no evidence behind them.
- When you need to replace a chart inside the page, lock the chart type from `catalog.md` and reuse the real implementation in the matching gallery, replacing only that chart slot.
- Mixing two report templates is forbidden, and so is keeping demo data, demo sources or demo conclusions.
