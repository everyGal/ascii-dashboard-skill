# Layout: Campaign Performance Dashboard

## Prompt

"I need a campaign performance view with spend, impressions, clicks, CTR, CPA as KPIs, a budget vs actual combo chart, and a campaign detail table."

## ASCII Wireframe

```
╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Campaign Performance Dashboard                                   [Campaign ▾] [Date ▾]     ║
╠══════════════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                              ║
║  ╭──────────╮  ╭──────────╮  ╭──────────╮  ╭──────────╮  ╭──────────╮                       ║
║  │  Spend   │  │  Impress │  │  Clicks  │  │   CTR    │  │   CPA    │                       ║
║  │ $125.0K  │  │   2.1M   │  │  84.0K   │  │  4.00%   │  │  $1.49   │                       ║
║  │ ▲ 8.2%   │  │ ▲ 15.1%  │  │ ▲ 11.4%  │  │ ▼ 0.3pp  │  │ ▼ 5.7%   │                       ║
║  ╰──────────╯  ╰──────────╯  ╰──────────╯  ╰──────────╯  ╰──────────╯                       ║
║                                                                                              ║
║  ╭──────────────────────────────────────────────╮  ╭────────────────────────────╮            ║
║  │ Budget vs Actual Spend                       │  │ CTR by Channel             │            ║
║  │                                              │  │                            │            ║
║  │  $30K ┤  ╔══╗                                │  │  Paid Search  ████████ 5.2%│            ║
║  │  $25K ┤  ║  ║  ╔══╗                          │  │  Social       ██████  3.8% │            ║
║  │  $20K ┤  ║▓▓║  ║  ║  ╔══╗                    │  │  Display      ████    2.4% │            ║
║  │  $15K ┤  ║▓▓║  ║▓▓║  ║  ║  ╔══╗              │  │  Email        ███████ 4.7% │            ║
║  │  $10K ┤  ║▓▓║  ║▓▓║  ║▓▓║  ║▓▓║  ╔══╗        │  │  Video        █████   3.1% │            ║
║  │   $5K ┤  ║▓▓║  ║▓▓║  ║▓▓║  ║▓▓║  ║▓▓║        │  │  Native       ██████  3.6% │            ║
║  │       ├──╚══╝──╚══╝──╚══╝──╚══╝──╚══╝──      │  │                            │            ║
║  │       Jan  Feb  Mar  Apr  May                 │  │                            │            ║
║  │  ░░ Budget  ▓▓ Actual  ── Trend               │  │                            │            ║
║  ╰──────────────────────────────────────────────╯  ╰────────────────────────────╯            ║
║                                                                                              ║
║  ╭──────────────────────────────────────────────────────────────────────────────────╮        ║
║  │ Campaign Detail Table                                                            │        ║
║  │                                                                                  │        ║
║  │  Campaign       │ Channel     │  Spend  │ Impress  │ Clicks │  CTR  │   CPA      │        ║
║  │  ───────────────┼─────────────┼─────────┼──────────┼────────┼───────┼─────────    │        ║
║  │  Spring Launch  │ Paid Search │ $32.5K  │  580K    │ 30.2K  │ 5.2%  │  $1.08     │        ║
║  │  Brand Aware    │ Social      │ $28.1K  │  620K    │ 23.6K  │ 3.8%  │  $1.19     │        ║
║  │  Retargeting    │ Display     │ $22.4K  │  410K    │  9.8K  │ 2.4%  │  $2.29     │        ║
║  │  Newsletter     │ Email       │ $18.7K  │  290K    │ 13.6K  │ 4.7%  │  $1.38     │        ║
║  │  Product Demo   │ Video       │ $23.3K  │  200K    │  6.8K  │ 3.4%  │  $3.43     │        ║
║  ╰──────────────────────────────────────────────────────────────────────────────────╯        ║
║                                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝
```

## JSON Spec

```json
{
  "dashboard": {
    "title": "Campaign Performance Dashboard",
    "layout": {
      "columns": 12,
      "rows": "auto"
    },
    "filters": [
      {
        "field": "Campaign",
        "type": "dropdown",
        "default": "All"
      },
      {
        "field": "Date",
        "type": "date_range",
        "default": "Last 6 Months"
      }
    ],
    "widgets": [
      {
        "id": "kpi_spend",
        "type": "kpi",
        "title": "Spend",
        "grid": { "col": 1, "row": 1, "width": 2, "height": 1 },
        "value_field": "Spend",
        "previous_field": "Previous Spend",
        "comparison": "percent_change",
        "format": "currency"
      },
      {
        "id": "kpi_impressions",
        "type": "kpi",
        "title": "Impressions",
        "grid": { "col": 3, "row": 1, "width": 2, "height": 1 },
        "value_field": "Impressions",
        "previous_field": "Previous Impressions",
        "comparison": "percent_change",
        "format": "number_abbreviated"
      },
      {
        "id": "kpi_clicks",
        "type": "kpi",
        "title": "Clicks",
        "grid": { "col": 5, "row": 1, "width": 2, "height": 1 },
        "value_field": "Clicks",
        "previous_field": "Previous Clicks",
        "comparison": "percent_change",
        "format": "number_abbreviated"
      },
      {
        "id": "kpi_ctr",
        "type": "kpi",
        "title": "CTR",
        "grid": { "col": 7, "row": 1, "width": 2, "height": 1 },
        "value_field": "CTR",
        "previous_field": "Previous CTR",
        "comparison": "absolute_change",
        "format": "percent"
      },
      {
        "id": "kpi_cpa",
        "type": "kpi",
        "title": "CPA",
        "grid": { "col": 9, "row": 1, "width": 2, "height": 1 },
        "value_field": "CPA",
        "previous_field": "Previous CPA",
        "comparison": "percent_change",
        "format": "currency"
      },
      {
        "id": "budget_vs_actual",
        "type": "combo",
        "title": "Budget vs Actual Spend",
        "grid": { "col": 1, "row": 2, "width": 7, "height": 2 },
        "x_field": "Month",
        "combo": {
          "primary_field": "Budget",
          "primary_type": "bar",
          "secondary_field": "Actual",
          "secondary_type": "line"
        }
      },
      {
        "id": "ctr_by_channel",
        "type": "bar",
        "title": "CTR by Channel",
        "grid": { "col": 8, "row": 2, "width": 5, "height": 2 },
        "category_field": "Channel",
        "value_field": "CTR",
        "horizontal": true
      },
      {
        "id": "campaign_detail_table",
        "type": "table",
        "title": "Campaign Detail Table",
        "grid": { "col": 1, "row": 4, "width": 12, "height": 2 },
        "category_field": "Campaign",
        "value_field": "Spend",
        "columns": ["Campaign", "Channel", "Spend", "Impressions", "Clicks", "CTR", "CPA"]
      }
    ]
  }
}
```

## Notes

- The combo chart uses bars for Budget and a line overlay for Actual spend, showing the gap visually.
- CTR by Channel uses a horizontal bar chart for easy label readability.
- Five KPIs span columns 1-10 at width 2 each.
- The combo chart and bar chart share row 2 with a 7:5 column split.
- The campaign detail table provides drill-down data at the bottom, spanning all 12 columns.
- CPA KPI uses inverted comparison logic (lower is better), so the down arrow is positive.
