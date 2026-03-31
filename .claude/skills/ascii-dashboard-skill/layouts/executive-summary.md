# Layout: Executive Summary Dashboard

## Prompt

"Executive summary: revenue, pipeline, win rate, deal size KPIs, a revenue treemap by segment, monthly trend line, and a highlight table of top accounts."

## ASCII Wireframe

```
╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Executive Summary                                         [Quarter ▾] [Region ▾]           ║
╠══════════════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                              ║
║  ╭─────────────╮  ╭─────────────╮  ╭─────────────╮  ╭─────────────╮                         ║
║  │   Revenue   │  │  Pipeline   │  │  Win Rate   │  │  Avg Deal   │                         ║
║  │   $4.2M     │  │   $12.8M    │  │   34.5%     │  │   $48.2K    │                         ║
║  │  ▲ 18.3%    │  │  ▲ 22.1%    │  │  ▲ 3.2pp    │  │  ▼ 5.1%     │                         ║
║  │  vs prior Q │  │  vs prior Q │  │  vs prior Q │  │  vs prior Q │                         ║
║  ╰─────────────╯  ╰─────────────╯  ╰─────────────╯  ╰─────────────╯                         ║
║                                                                                              ║
║  ╭──────────────────────────────────╮  ╭──────────────────────────────────╮                  ║
║  │ Revenue by Segment (Treemap)    │  │ Monthly Revenue Trend             │                  ║
║  │                                  │  │                                   │                  ║
║  │  ┌──────────────┬────────┐      │  │  $500K ┤                    ╱     │                  ║
║  │  │              │        │      │  │  $450K ┤               ╱╲ ╱      │                  ║
║  │  │  Enterprise  │ Mid-   │      │  │  $400K ┤          ╱╲  ╱  ╲       │                  ║
║  │  │   $2.1M      │ Market │      │  │  $350K ┤     ╱╲  ╱  ╲╱          │                  ║
║  │  │   50.0%      │ $1.1M  │      │  │  $300K ┤╱╲  ╱  ╲╱               │                  ║
║  │  │              │ 26.2%  │      │  │  $250K ┤  ╲╱                      │                  ║
║  │  ├──────────────┼───┬────┤      │  │        ├──┬──┬──┬──┬──┬──┬──┬──  │                  ║
║  │  │   SMB        │Gov│    │      │  │        Jan Feb Mar Apr May Jun Jul│                  ║
║  │  │   $0.7M      │$0 │    │      │  │                                   │                  ║
║  │  │   16.7%      │7% │    │      │  │  ── Revenue  ╌╌ Target            │                  ║
║  │  └──────────────┴───┴────┘      │  │                                   │                  ║
║  ╰──────────────────────────────────╯  ╰──────────────────────────────────╯                  ║
║                                                                                              ║
║  ╭──────────────────────────────────────────────────────────────────────────────────╮        ║
║  │ Top Accounts                                                                     │        ║
║  │                                                                                  │        ║
║  │  Account          │ Revenue  │ Pipeline │ Win Rate │ Deals │ Segment              │        ║
║  │  ─────────────────┼──────────┼──────────┼──────────┼───────┼───────────            │        ║
║  │  Acme Corp        │ ██ $820K │ ██ $1.2M │ ██  42%  │  18   │ Enterprise            │        ║
║  │  GlobalTech       │ ██ $645K │ ██ $980K │ ██  38%  │  14   │ Enterprise            │        ║
║  │  Pinnacle Inc     │ █  $410K │ █  $720K │ ██  35%  │  11   │ Mid-Market            │        ║
║  │  Summit LLC       │ █  $380K │ █  $540K │ █   28%  │   9   │ Mid-Market            │        ║
║  │  Nova Systems     │ █  $290K │ █  $480K │ ██  41%  │   7   │ SMB                   │        ║
║  ╰──────────────────────────────────────────────────────────────────────────────────╯        ║
║                                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝
```

## JSON Spec

```json
{
  "dashboard": {
    "title": "Executive Summary",
    "layout": {
      "columns": 12,
      "rows": "auto"
    },
    "filters": [
      {
        "field": "Quarter",
        "type": "dropdown",
        "default": "Q4 2025"
      },
      {
        "field": "Region",
        "type": "dropdown",
        "default": "All"
      }
    ],
    "widgets": [
      {
        "id": "kpi_revenue",
        "type": "kpi",
        "title": "Revenue",
        "grid": { "col": 1, "row": 1, "width": 3, "height": 1 },
        "value_field": "Revenue",
        "previous_field": "Previous Revenue",
        "comparison": "percent_change",
        "format": "currency",
        "subtitle": "vs prior Q"
      },
      {
        "id": "kpi_pipeline",
        "type": "kpi",
        "title": "Pipeline",
        "grid": { "col": 4, "row": 1, "width": 3, "height": 1 },
        "value_field": "Pipeline",
        "previous_field": "Previous Pipeline",
        "comparison": "percent_change",
        "format": "currency",
        "subtitle": "vs prior Q"
      },
      {
        "id": "kpi_win_rate",
        "type": "kpi",
        "title": "Win Rate",
        "grid": { "col": 7, "row": 1, "width": 3, "height": 1 },
        "value_field": "Win Rate",
        "previous_field": "Previous Win Rate",
        "comparison": "absolute_change",
        "format": "percent",
        "subtitle": "vs prior Q"
      },
      {
        "id": "kpi_avg_deal",
        "type": "kpi",
        "title": "Avg Deal Size",
        "grid": { "col": 10, "row": 1, "width": 3, "height": 1 },
        "value_field": "Avg Deal Size",
        "previous_field": "Previous Avg Deal Size",
        "comparison": "percent_change",
        "format": "currency",
        "subtitle": "vs prior Q"
      },
      {
        "id": "revenue_treemap",
        "type": "treemap",
        "title": "Revenue by Segment",
        "grid": { "col": 1, "row": 2, "width": 6, "height": 2 },
        "category_field": "Segment",
        "value_field": "Revenue",
        "label_field": "Segment"
      },
      {
        "id": "monthly_revenue_trend",
        "type": "line",
        "title": "Monthly Revenue Trend",
        "grid": { "col": 7, "row": 2, "width": 6, "height": 2 },
        "x_field": "Month",
        "y_field": "Revenue",
        "x_type": "ordinal"
      },
      {
        "id": "top_accounts_table",
        "type": "table",
        "title": "Top Accounts",
        "grid": { "col": 1, "row": 4, "width": 12, "height": 2 },
        "category_field": "Account",
        "value_field": "Revenue",
        "columns": ["Account", "Revenue", "Pipeline", "Win Rate", "Deals", "Segment"]
      }
    ]
  }
}
```

## Notes

- The 4 KPI cards use width 3 each, filling the full 12-column row evenly.
- The treemap and line chart split row 2 with a 6:6 even split.
- The line chart tracks monthly revenue against a target line for variance analysis.
- The top accounts table uses a highlight variant to show color intensity per cell.
