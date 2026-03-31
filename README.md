# ascii-wireframe-skill

A Claude Code skill that converts plain-English dashboard descriptions into **ASCII wireframes** and **JSON layout specs**.

## What It Does

Describe a dashboard in natural language → get back:

1. An ASCII wireframe you can review in the terminal
2. A structured `DashboardSpec` JSON for further use

**Example input:**
> "Sales dashboard with 4 KPI cards on top, a line chart showing monthly revenue, and a table of top 10 deals"

**Example output:**
```
┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐
│ Revenue  │ │  Deals   │ │Win Rate  │ │  ACV     │
│ $2.4M    │ │   187    │ │  64%     │ │ $12.8K   │
│ ▲ 18%   │ │ ▲ 23%   │ │ ▼ 2%    │ │ ▲ 9%    │
└──────────┘ └──────────┘ └──────────┘ └──────────┘
┌──────────────────────────────────────────────────┐
│  Monthly Revenue                                 │
│  2.5M│              ╭────╮                       │
│  2.0M│         ╭───╯    ╰──╮                     │
│  1.5M│    ╭───╯             ╰──                  │
│  1.0M│╭──╯                                      │
│      └──────────────────────────────────────     │
│       Jan  Feb  Mar  Apr  May  Jun               │
└──────────────────────────────────────────────────┘
┌──────────────────────────────────────────────────┐
│ Deal          │ Stage    │  Value  │ Close Date   │
├───────────────┼──────────┼─────────┼─────────────┤
│ Acme Corp     │ Proposal │ $48,000 │ 2024-03-31   │
│ Globex        │ Negotiat │ $32,500 │ 2024-04-15   │
│ Initech       │ Closed W │ $67,200 │ 2024-03-28   │
└──────────────────────────────────────────────────┘
```

## Installation

Drop the `ascii-wireframe-skill/` folder into your project's `.claude/skills/` directory:

```
your-project/
  .claude/
    skills/
      ascii-wireframe-skill/   ← place here
```

Claude Code will auto-load it. Invoke with:

```
/ascii-wireframe
```

Or describe what you want and Claude will pick it up automatically.

## Folder Structure

```
ascii-wireframe-skill/
├── SKILL.md                  # Main skill entrypoint — workflow, grid system, rules
├── components/               # Per-chart ASCII patterns and spec templates (31 types)
│   ├── kpi-card.md
│   ├── bar-chart.md
│   ├── line-chart.md
│   ├── pie-chart.md
│   ├── table.md
│   └── ...
├── layouts/                  # Full end-to-end dashboard examples (5 layouts)
│   ├── executive-summary.md
│   ├── sales-pipeline.md
│   ├── marketing-funnel.md
│   ├── campaign-performance.md
│   └── operations-overview.md
├── references/
│   ├── ascii-patterns.md     # Box-drawing chars, block fills, Unicode table
│   └── component-status.md   # Complexity tiers and tool compatibility notes
└── schemas/
    └── dashboard-spec.schema.json  # JSON Schema for DashboardSpec output
```

## Supported Chart Types

| Category | Types |
|----------|-------|
| KPI / Summary | KPI card, sparkline, bullet chart, gauge |
| Comparisons | Bar chart, lollipop, histogram, waterfall |
| Trends | Line chart, area chart, combo chart, stream graph |
| Part-of-whole | Pie/donut, treemap, sunburst, packed bubble |
| Distributions | Scatter, box plot, heatmap, calendar heatmap |
| Flow | Funnel, sankey, bump chart, slope chart |
| Relational | Network, radar, map |
| Specialized | Gantt, table |
| UI | Filter bar, text/header |

## Grid System

Dashboards use a 12-column grid. Every component has `col`, `width`, `row`, and `height` values:

```json
{
  "type": "bar_chart",
  "title": "Revenue by Region",
  "col": 1, "width": 6,
  "row": 2, "height": 3
}
```

See `SKILL.md` and `schemas/dashboard-spec.schema.json` for the full spec.
