# Component Status & Complexity Reference

This file helps set expectations when advising users on which chart types are easier or harder to implement in downstream tools.

## Complexity Tiers

| Tier | Label | Meaning |
|------|-------|---------|
| 1 | **Starter** | Natively supported in virtually every BI tool; little or no custom config |
| 2 | **Standard** | Broadly available; may require minor configuration or a plugin |
| 3 | **Advanced** | Available in most modern tools but often needs custom setup, extensions, or D3 |
| 4 | **Expert** | Rarely built-in; typically requires custom code, D3.js, or a specialist library |

---

## Tier 1 — Starter

Low friction. Recommend freely.

| Component File | Spec Type(s) | Notes |
|---|---|---|
| `kpi-card.md` | `kpi` | "Scorecard" or "big number" in all major BI tools |
| `bar-chart.md` | `bar` (standard, horizontal) | One of the most universally supported chart types |
| `line-chart.md` | `line`, `time_series` | Second most common chart type; natively in every tool |
| `pie-chart.md` | `pie` (incl. donut) | Universal; donut is a style variant of pie |
| `table.md` | `table` | Simple text table is available everywhere |
| `filter-bar.md` | `filter_bar` | Dropdowns and date pickers are native UI controls |
| `text-header.md` | `text_header` | Plain text/markdown widget available in all tools |

---

## Tier 2 — Standard

Widely available; minor setup may be needed.

| Component File | Spec Type(s) | Notes |
|---|---|---|
| `bar-chart.md` | `bar` (stacked, grouped) | Variants of bar; most tools support with a toggle |
| `line-chart.md` | `multi_series` | Most tools support with a series field |
| `area-chart.md` | `area` (single, stacked) | Common; stacked variant may need explicit config |
| `scatter-chart.md` | `scatter` | Standard in most BI tools |
| `combo-chart.md` | `combo` | Dual-axis bar+line; supported in most modern tools |
| `table.md` | `table` (highlight) | Color-coded cells; available as conditional formatting |
| `heatmap.md` | `heatmap` | Matrix heatmap supported in most tools |
| `treemap.md` | `treemap` | Available in Tableau, Power BI, Looker natively |
| `funnel.md` | `funnel` | Native in most BI tools; occasionally a plugin |
| `histogram.md` | `histogram` | Available natively; sometimes needs bin config |
| `sparkline.md` | `sparkline` | Inline spark charts; table sparkline may need extension |
| `gauge.md` | `gauge` | Dial/needle gauge; native in most tools |

---

## Tier 3 — Advanced

Available but often needs custom configuration or extensions.

| Component File | Spec Type | Notes |
|---|---|---|
| `scatter-chart.md` | `scatter` (bubble variant) | Bubble (sized scatter) needs a size field; some tools require plugin |
| `waterfall.md` | `waterfall` | Native in Power BI and Tableau; custom in others |
| `bullet-chart.md` | `bullet_chart` | Requires a range layer + target marker; extension in some tools |
| `box-plot.md` | `box_plot` | Statistical chart; native in some tools, D3 extension in others |
| `gantt.md` | `gantt` | Project-style timeline; native in few BI tools |
| `calendar-heatmap.md` | `calendar_heatmap` | Requires date-binned heatmap; custom in most tools |
| `lollipop.md` | `lollipop` | Bar+dot hybrid; usually custom or a plugin |
| `slope-chart.md` | `slope_chart` | Before/after comparison line; custom in most tools |
| `radar.md` | `radar` | Spider/polar chart; native in some tools (Tableau, Power BI) |
| `map.md` | `map` | Filled/symbol map; requires geographic data and tool integration |

---

## Tier 4 — Expert

Custom code typically required. Flag complexity upfront.

| Component File | Spec Type | Notes |
|---|---|---|
| `sankey.md` | `sankey` | Flow diagram; D3.js or specific library required |
| `bump-chart.md` | `bump_chart` | Rank-over-time lines; rarely native; D3 or Vega |
| `sunburst.md` | `sunburst` | Radial hierarchy; D3.js or custom viz extension |
| `stream-graph.md` | `stream_graph` | Flowing stacked area; D3.js or custom |
| `packed-bubble.md` | `packed_bubble` | Circle-pack layout; D3 force simulation |
| `network.md` | `network` | Node-link graph; D3 force or dedicated graph library |

---

## Choosing the Right Complexity for the Audience

| Audience | Recommendation |
|---|---|
| **Business users / no-code tools** | Stick to Tier 1–2. Avoid Tier 3+ unless the user confirms technical support. |
| **BI developers (Tableau, Power BI, Looker)** | Tier 1–3 are fine. Flag Tier 4 as requiring custom extensions. |
| **Engineering / front-end teams** | All tiers available; Tier 4 needs D3.js or a charting library like Recharts, Chart.js, or Observable Plot. |
| **Prototype / mockup only** | All tiers are fine to wireframe — just note complexity in the spec. |

---

## Implementation Notes by Tool

| Tool | Tier 1 | Tier 2 | Tier 3 | Tier 4 |
|------|--------|--------|--------|--------|
| Tableau | Native | Native | Some native, some extension | Extension or custom viz |
| Power BI | Native | Native | Some native (waterfall, decomp tree) | Custom visual (.pbiviz) |
| Looker / LookML | Native | Native | Explore + custom vis | Custom vis SDK |
| Metabase | Native | Most native | Limited (gantt, bullet = no) | Not supported natively |
| Grafana | Native | Native | Panel plugins | Custom panel plugin |
| Observable / D3.js | All tiers equally supported via code |
| React (Recharts, Victory, Nivo) | All tiers supported with appropriate library selection |
