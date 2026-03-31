# Layout: Sales Pipeline Dashboard

## Prompt

"Sales pipeline dashboard with pipeline value, deals, avg deal size, close rate KPIs, a funnel chart, a waterfall showing pipeline changes, and a deal scatter plot."

## ASCII Wireframe

```
╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Sales Pipeline Dashboard                                      [Quarter ▾] [Rep ▾]          ║
╠══════════════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                              ║
║  ╭─────────────╮  ╭─────────────╮  ╭─────────────╮  ╭─────────────╮                         ║
║  │  Pipeline   │  │ Active Deals│  │ Avg Deal Sz │  │ Close Rate  │                         ║
║  │   $8.4M     │  │    142      │  │   $59.2K    │  │   28.3%     │                         ║
║  │  ▲ 14.7%    │  │  ▲ 8 deals  │  │  ▲ 6.1%     │  │  ▼ 2.1pp   │                         ║
║  ╰─────────────╯  ╰─────────────╯  ╰─────────────╯  ╰─────────────╯                         ║
║                                                                                              ║
║  ╭──────────────────────╮  ╭──────────────────────╮  ╭──────────────────────╮                ║
║  │ Pipeline Funnel      │  │ Pipeline Changes     │  │ Deal Scatter         │                ║
║  │                      │  │ (Waterfall)          │  │                      │                ║
║  │  ┌──────────────┐    │  │                      │  │  $120K ┤        o    │                ║
║  │  │  Prospect    │    │  │  $10M ┤              │  │  $100K ┤   O      o  │                ║
║  │  │    $3.2M     │    │  │       │  ╔══╗        │  │   $80K ┤  o  O  o    │                ║
║  │  └──────────────┘    │  │  $8M  ┤  ║  ║ ┌──┐  │  │   $60K ┤ o O  o     │                ║
║  │    ┌──────────┐      │  │       │  ║  ║ │▒▒│  │  │   $40K ┤o  o o   o   │                ║
║  │    │ Qualify  │      │  │  $6M  ┤──╚══╝─┤▒▒├──│  │   $20K ┤  o     o    │                ║
║  │    │  $2.4M   │      │  │       │  Add  Lost  │  │        ├──┬──┬──┬──  │                ║
║  │    └──────────┘      │  │  $4M  ┤  ╔══╗ ╔══╗  │  │        10 20 30 40   │                ║
║  │      ┌──────┐        │  │       │  ║  ║ ║  ║  │  │        Days in Stage  │                ║
║  │      │Propose│       │  │  $2M  ┤  ║  ║ ║  ║  │  │                      │                ║
║  │      │ $1.6M │       │  │       ├──╚══╝─╚══╝  │  │  o = deal            │                ║
║  │      └──────┘        │  │       Open +New -Lst │  │  size = deal value   │                ║
║  │       ┌────┐         │  │            +Won Cls  │  │                      │                ║
║  │       │Neg │         │  │                      │  │                      │                ║
║  │       │$0.8M│        │  │                      │  │                      │                ║
║  │       └────┘         │  │                      │  │                      │                ║
║  │        ┌──┐          │  │                      │  │                      │                ║
║  │        │$0.4M        │  │                      │  │                      │                ║
║  │        └──┘ Won      │  │                      │  │                      │                ║
║  ╰──────────────────────╯  ╰──────────────────────╯  ╰──────────────────────╯                ║
║                                                                                              ║
║  ╭──────────────────────────────────────────────────────────────────────────────────╮        ║
║  │ Deal Details Table                                                               │        ║
║  │                                                                                  │        ║
║  │  Deal Name       │ Account     │  Value  │  Stage    │ Days  │ Close Date │ Rep   │        ║
║  │  ────────────────┼─────────────┼─────────┼───────────┼───────┼────────────┼────── │        ║
║  │  Platform Upgrade│ Acme Corp   │ $112K   │ Negotiate │  34   │ 2025-12-15 │ Sarah │        ║
║  │  Cloud Migration │ TechStart   │  $95K   │ Propose   │  28   │ 2025-12-22 │ James │        ║
║  │  API Integration │ DataFlow    │  $78K   │ Qualify   │  15   │ 2026-01-10 │ Maria │        ║
║  │  License Renewal │ OldCo       │  $64K   │ Negotiate │  42   │ 2025-12-08 │ Sarah │        ║
║  │  New Deployment  │ FastGrow    │  $51K   │ Prospect  │   7   │ 2026-02-01 │ James │        ║
║  ╰──────────────────────────────────────────────────────────────────────────────────╯        ║
║                                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝
```

## JSON Spec

```json
{
  "dashboard": {
    "title": "Sales Pipeline Dashboard",
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
        "field": "Rep",
        "type": "dropdown",
        "default": "All"
      }
    ],
    "widgets": [
      {
        "id": "kpi_pipeline_value",
        "type": "kpi",
        "title": "Pipeline Value",
        "grid": { "col": 1, "row": 1, "width": 3, "height": 1 },
        "value_field": "Pipeline Value",
        "previous_field": "Previous Pipeline Value",
        "comparison": "percent_change",
        "format": "currency"
      },
      {
        "id": "kpi_active_deals",
        "type": "kpi",
        "title": "Active Deals",
        "grid": { "col": 4, "row": 1, "width": 3, "height": 1 },
        "value_field": "Active Deals",
        "previous_field": "Previous Active Deals",
        "comparison": "absolute_change",
        "format": "number"
      },
      {
        "id": "kpi_avg_deal_size",
        "type": "kpi",
        "title": "Avg Deal Size",
        "grid": { "col": 7, "row": 1, "width": 3, "height": 1 },
        "value_field": "Avg Deal Size",
        "previous_field": "Previous Avg Deal Size",
        "comparison": "percent_change",
        "format": "currency"
      },
      {
        "id": "kpi_close_rate",
        "type": "kpi",
        "title": "Close Rate",
        "grid": { "col": 10, "row": 1, "width": 3, "height": 1 },
        "value_field": "Close Rate",
        "previous_field": "Previous Close Rate",
        "comparison": "absolute_change",
        "format": "percent"
      },
      {
        "id": "pipeline_funnel",
        "type": "funnel",
        "title": "Pipeline Funnel",
        "grid": { "col": 1, "row": 2, "width": 4, "height": 2 },
        "category_field": "Stage",
        "value_field": "Pipeline Value",
        "stages": ["Prospect", "Qualify", "Propose", "Negotiate", "Won"]
      },
      {
        "id": "pipeline_waterfall",
        "type": "waterfall",
        "title": "Pipeline Changes",
        "grid": { "col": 5, "row": 2, "width": 4, "height": 2 },
        "category_field": "Change Type",
        "value_field": "Amount",
        "categories": ["Opening", "New Added", "Lost", "Won", "Closing"]
      },
      {
        "id": "deal_scatter",
        "type": "scatter",
        "title": "Deal Scatter",
        "grid": { "col": 9, "row": 2, "width": 4, "height": 2 },
        "x_field": "Days in Stage",
        "y_field": "Deal Value",
        "size_field": "Deal Value",
        "color_field": "Stage"
      },
      {
        "id": "deal_details_table",
        "type": "table",
        "title": "Deal Details Table",
        "grid": { "col": 1, "row": 4, "width": 12, "height": 2 },
        "category_field": "Deal Name",
        "value_field": "Value",
        "columns": ["Deal Name", "Account", "Value", "Stage", "Days", "Close Date", "Rep"]
      }
    ]
  }
}
```

## Notes

- The three mid-row charts use a 4:4:4 even split across the 12 columns.
- The 4 KPIs use width 3 each, filling the full 12-column row.
- The detail table at the bottom provides per-deal drill-down across all 12 columns.
- The scatter plot plots deals by days-in-stage vs. value, with bubble size mapped to deal value and color mapped to stage.
