---
name: ascii-wireframe
description: Convert plain-English dashboard descriptions into ASCII wireframes and structured JSON layout specs. Use when a user asks to design, wireframe, or sketch out a dashboard.
---

# ASCII Dashboard Wireframing Skill

## What This Skill Does

Converts natural language dashboard descriptions into two outputs:
1. **ASCII wireframe** — a visual layout using box-drawing characters, reviewable in the terminal
2. **JSON spec** — a structured `DashboardSpec` describing the layout for further use

## Workflow

```
User describes dashboard → Generate ASCII wireframe → User reviews/iterates → Finalize JSON spec
```

### Step 1: Understand the Request
Parse the user's description for:
- **KPIs/metrics** they want to highlight
- **Chart types** (bar, line, pie, table, etc.)
- **Relationships** between data points (trends, comparisons, breakdowns)
- **Filters** or controls needed

### Step 2: Generate ASCII Wireframe
- Read the relevant component files from `components/` for ASCII patterns
- Arrange components on a **12-column grid**
- Populate with **realistic sample data** (not placeholders like `{{value}}`)
- Present the wireframe and **wait for user feedback**

### Step 3: Iterate
- Apply user feedback: "move X left", "swap pie for bar", "add a filter", "make the table wider"
- Re-render the ASCII wireframe
- Repeat until the user approves

### Step 4: Generate JSON Spec
- Output the final `DashboardSpec` JSON matching the approved wireframe
- Validate against the schema in `schemas/dashboard-spec.schema.json`
- Ensure no grid overlaps (widgets must not occupy the same cells)

## Grid System

The dashboard uses a **12-column grid** (like Bootstrap). Each row can hold widgets totaling up to 12 columns.

```
Col:  1    2    3    4    5    6    7    8    9   10   11   12
     ┌────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┐
     │    │    │    │    │    │    │    │    │    │    │    │    │
     └────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴────┘
```

**Grid rules:**
- `col` starts at 1 (1-indexed)
- `width` is in columns (1-12)
- `col + width - 1` must not exceed 12
- Widgets in the same row must not overlap horizontally
- `row` starts at 1, auto-increments
- `height` is in row units (typically 1 for KPIs, 2 for charts, 2-3 for tables)

## ASCII Conventions

### Dashboard Frame
```
╔══════════════════════════════════════════════════════════════╗
║  Dashboard Title                              [Filter ▾]    ║
╠══════════════════════════════════════════════════════════════╣
║  (content area)                                              ║
╚══════════════════════════════════════════════════════════════╝
```

### Widget Borders
```
╭─────────────────╮
│  Widget Title    │
│  (content)       │
╰─────────────────╯
```

### Refer to `references/ascii-patterns.md` for:
- Chart-specific ASCII patterns (bars, lines, pies, tables)
- Box-drawing character reference
- Sizing conventions

## Component Library

Each component file in `components/` provides:
1. ASCII pattern with sample data
2. JSON spec template (required/optional fields)
3. Sizing guidelines (typical grid dimensions)
4. Complexity tier (for estimating implementation effort)

### Standard Components (Common Chart Types)

| Component File | Spec Type(s) |
|---|---|
| `kpi-card.md` | `kpi` |
| `bar-chart.md` | `bar` (vertical, horizontal, stacked, grouped) |
| `line-chart.md` | `line`, `multi_series`, `time_series` |
| `area-chart.md` | `area` (single, stacked) |
| `pie-chart.md` | `pie` (pie, donut variant) |
| `table.md` | `table` (text table, highlight table) |
| `scatter-chart.md` | `scatter` (scatter, bubble variant) |
| `combo-chart.md` | `combo` |

### Extended Components (Advanced Chart Types)

| Component File | Spec Type |
|---|---|
| `heatmap.md` | `heatmap` |
| `treemap.md` | `treemap` |
| `funnel.md` | `funnel` |
| `waterfall.md` | `waterfall` |
| `bullet-chart.md` | `bullet_chart` |
| `histogram.md` | `histogram` |
| `gauge.md` | `gauge` |
| `gantt.md` | `gantt` |
| `box-plot.md` | `box_plot` |
| `sparkline.md` | `sparkline` |
| `calendar-heatmap.md` | `calendar_heatmap` |
| `lollipop.md` | `lollipop` |
| `slope-chart.md` | `slope_chart` |
| `packed-bubble.md` | `packed_bubble` |
| `map.md` | `map` |
| `sankey.md` | `sankey` |
| `radar.md` | `radar` |
| `bump-chart.md` | `bump_chart` |
| `sunburst.md` | `sunburst` |
| `stream-graph.md` | `stream_graph` |
| `network.md` | `network` |

### UI Elements (No Chart Needed)

| Component File | Spec Type |
|---|---|
| `filter-bar.md` | `filter_bar` |
| `text-header.md` | `text_header` |

## JSON Spec Structure

```json
{
  "dashboard": {
    "title": "Dashboard Title",
    "layout": {
      "columns": 12,
      "rows": "auto"
    },
    "filters": [],
    "widgets": []
  }
}
```

Each widget follows the structure defined in its component file. All widgets must have:
- `id` — unique identifier (snake_case)
- `type` — one of the supported type enums
- `title` — display title
- `grid` — `{ "col": int, "row": int, "width": int, "height": int }`

## Layout Examples

See `layouts/` for complete prompt-to-wireframe-to-spec examples:
- `marketing-funnel.md` — KPIs + funnel + trend + table
- `campaign-performance.md` — KPIs + bar + combo + table
- `executive-summary.md` — KPI row + treemap + line + highlight table
- `sales-pipeline.md` — KPIs + funnel + waterfall + scatter
- `operations-overview.md` — KPIs + gantt + heatmap + gauge

## Component Complexity Reference

See `references/component-status.md` for a breakdown of chart types by rendering complexity — useful when advising users on which chart types are easier or harder to implement downstream.
