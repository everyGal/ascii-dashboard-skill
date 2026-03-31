# Layout: Marketing Funnel Dashboard

## Prompt

"Build a marketing funnel dashboard showing sessions through to opportunities, with conversion rates, a weekly trend, channel breakdown, and a detail table."

## ASCII Wireframe

```
╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Marketing Funnel Dashboard                                           [Date Range ▾]        ║
╠══════════════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                              ║
║  ╭──────────╮   ╭──────────╮   ╭──────────╮   ╭──────────╮   ╭──────────╮                   ║
║  │ Sessions │   │  Leads   │   │  MQLs    │   │  SQLs    │   │   Opps   │                   ║
║  │  45,200  │──▷│  3,800   │──▷│  1,240   │──▷│   560    │──▷│   180    │                   ║
║  │ ▲ 12.3%  │   │  8.4%    │   │  32.6%   │   │  45.2%   │   │  32.1%   │                   ║
║  │ vs prior │   │ cvr rate │   │ cvr rate │   │ cvr rate │   │ cvr rate │                   ║
║  ╰──────────╯   ╰──────────╯   ╰──────────╯   ╰──────────╯   ╰──────────╯                   ║
║                                                                                              ║
║  ╭──────────────────────────────────────────────╮  ╭────────────────────────────╮            ║
║  │ Weekly Funnel Trend                          │  │ Channel Breakdown          │            ║
║  │                                              │  │                            │            ║
║  │  4.8K ┤                          ╱╲           │  │       ╭────╮               │            ║
║  │  4.0K ┤              ╱╲    ╱╲  ╱  ╲          │  │    ╭──╯    ╰──╮            │            ║
║  │  3.2K ┤         ╱╲  ╱  ╲  ╱  ╲╱    ╲         │  │   ╱  Organic   ╲           │            ║
║  │  2.4K ┤    ╱╲  ╱  ╲╱    ╲╱                   │  │  │   38.2%      │          │            ║
║  │  1.6K ┤   ╱  ╲╱                              │  │  │ Paid ╱ Email │          │            ║
║  │  0.8K ┤  ╱                                    │  │  │ 28.1%╱ 18.4% │          │            ║
║  │       ├──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──   │  │   ╲ Social     ╱           │            ║
║  │       W1 W2 W3 W4 W5 W6 W7 W8 W9 W10W11W12  │  │    ╰─ 15.3% ─╯            │            ║
║  │  ── Sessions  ── Leads  ── MQLs               │  │                            │            ║
║  ╰──────────────────────────────────────────────╯  ╰────────────────────────────╯            ║
║                                                                                              ║
║  ╭──────────────────────────────────────────────────────────────────────────────────╮        ║
║  │ Conversion Detail Table                                                         │        ║
║  │                                                                                  │        ║
║  │  Stage        │ Volume  │ Cvr Rate │ Avg Days │ Top Channel  │ WoW Change        │        ║
║  │  ─────────────┼─────────┼──────────┼──────────┼──────────────┼────────────        │        ║
║  │  Sessions     │ 45,200  │   --     │   --     │ Organic      │ ▲ 12.3%           │        ║
║  │  Leads        │  3,800  │   8.4%   │   2.1    │ Paid Search  │ ▲  5.7%           │        ║
║  │  MQLs         │  1,240  │  32.6%   │   4.3    │ Email        │ ▼  2.1%           │        ║
║  │  SQLs         │    560  │  45.2%   │   6.8    │ Organic      │ ▲  8.9%           │        ║
║  │  Opps         │    180  │  32.1%   │  11.2    │ Referral     │ ▲  3.4%           │        ║
║  ╰──────────────────────────────────────────────────────────────────────────────────╯        ║
║                                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝
```

## JSON Spec

```json
{
  "dashboard": {
    "title": "Marketing Funnel Dashboard",
    "layout": {
      "columns": 12,
      "rows": "auto"
    },
    "filters": [
      {
        "field": "Date",
        "type": "date_range",
        "default": "Last 12 Weeks"
      }
    ],
    "widgets": [
      {
        "id": "kpi_sessions",
        "type": "kpi",
        "title": "Sessions",
        "grid": { "col": 1, "row": 1, "width": 2, "height": 1 },
        "value_field": "Sessions",
        "previous_field": "Previous Sessions",
        "comparison": "percent_change",
        "subtitle": "vs prior week"
      },
      {
        "id": "kpi_leads",
        "type": "kpi",
        "title": "Leads",
        "grid": { "col": 3, "row": 1, "width": 2, "height": 1 },
        "value_field": "Leads",
        "subtitle": "8.4% cvr rate"
      },
      {
        "id": "kpi_mqls",
        "type": "kpi",
        "title": "MQLs",
        "grid": { "col": 5, "row": 1, "width": 2, "height": 1 },
        "value_field": "MQLs",
        "subtitle": "32.6% cvr rate"
      },
      {
        "id": "kpi_sqls",
        "type": "kpi",
        "title": "SQLs",
        "grid": { "col": 7, "row": 1, "width": 2, "height": 1 },
        "value_field": "SQLs",
        "subtitle": "45.2% cvr rate"
      },
      {
        "id": "kpi_opps",
        "type": "kpi",
        "title": "Opportunities",
        "grid": { "col": 9, "row": 1, "width": 2, "height": 1 },
        "value_field": "Opportunities",
        "subtitle": "32.1% cvr rate"
      },
      {
        "id": "weekly_funnel_trend",
        "type": "multi_series",
        "title": "Weekly Funnel Trend",
        "grid": { "col": 1, "row": 2, "width": 7, "height": 2 },
        "x_field": "Week",
        "x_type": "ordinal",
        "series": [
          { "field": "Sessions", "label": "Sessions" },
          { "field": "Leads", "label": "Leads" },
          { "field": "MQLs", "label": "MQLs" }
        ]
      },
      {
        "id": "channel_breakdown",
        "type": "pie",
        "title": "Channel Breakdown",
        "grid": { "col": 8, "row": 2, "width": 5, "height": 2 },
        "category_field": "Channel",
        "value_field": "Sessions"
      },
      {
        "id": "conversion_detail_table",
        "type": "table",
        "title": "Conversion Detail Table",
        "grid": { "col": 1, "row": 4, "width": 12, "height": 2 },
        "category_field": "Stage",
        "value_field": "Volume",
        "columns": ["Stage", "Volume", "Cvr Rate", "Avg Days", "Top Channel", "WoW Change"]
      }
    ]
  }
}
```

## Notes

- KPI cards are arranged left-to-right to represent funnel progression from Sessions to Opportunities.
- Conversion rates appear as subtitle metrics beneath each KPI value.
- The trend line chart and pie chart share row 2 with a 7:5 column split.
- The detail table spans the full 12-column width at the bottom.
- The `multi_series` type renders multiple lines on a single chart for Sessions, Leads, and MQLs.
- The 5 KPIs use width 2 each, occupying columns 1-2, 3-4, 5-6, 7-8, 9-10 (10 of 12 columns).
