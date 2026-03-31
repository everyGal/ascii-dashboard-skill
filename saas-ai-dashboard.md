# SaaS AI Startup — Executive KPI Dashboard

> **Skill showcase** — Built with the [`ascii-dashboard-skill`](https://github.com/everygal/ascii-dashboard-skill).
> Converts a plain-English dashboard brief into a monospace ASCII wireframe + a structured JSON layout spec —
> ready to hand off to any BI tool (Tableau, Looker, Power BI, Grafana, Observable, React).

---

## Full Dashboard Wireframe

```
╔══════════════════════════════════════════════════════════════════════════════╗
║        ◈  NexaAI Platform  ·  Executive KPI Dashboard  ·  March 2026  ◈     ║
╚══════════════════════════════════════════════════════════════════════════════╝

┌─ GROWTH METRICS ─────────────────────────────────────────────────────────────┐
│                                                                               │
│  ╭─────────────────╮  ╭─────────────────╮  ╭─────────────────╮  ╭──────────────────╮
│  │ MRR             │  │ ARR             │  │ Active Customers│  │ Net Churn Rate   │
│  │ $142,800        │  │ $1.71M          │  │ 1,284           │  │ 2.1%             │
│  │ ▲ +12.4% MoM    │  │ ▲ +12.4% YoY    │  │ ▲ +87 this mo   │  │ ▼ −0.3% vs Feb   │
│  ╰─────────────────╯  ╰─────────────────╯  ╰─────────────────╯  ╰──────────────────╯
│                                                                               │
└───────────────────────────────────────────────────────────────────────────────┘

╭───────────────────────────────────────────────────────────────────────────────╮
│  MRR Trend — Apr 2025 → Mar 2026                                              │
│                                                                               │
│  160K ┤                                                                 ╱     │
│  145K ┤                                                    ╱────────────      │
│  130K ┤                                       ╱────────────                   │
│  115K ┤                          ╱────────────                                │
│  100K ┤             ╱────────────                                             │
│   85K ┤  ╱──────────                                                          │
│   70K ┤╱                                                                      │
│       ┼─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬── │
│       Apr   May   Jun   Jul   Aug   Sep   Oct   Nov   Dec   Jan   Feb   Mar   │
╰───────────────────────────────────────────────────────────────────────────────╯

╭──────────────────────────────────╮  ╭────────────────────────────────────────╮
│  Trial → Paid Conversion         │  │  Top Customers by MRR                  │
│                                  │  │                                        │
│  Visitors   ████████████  18,400 │  │  ┌─────────────────┬──────────┬───────┐│
│                   71.2%          │  │  │ Company         │ Plan     │ MRR   ││
│  Sign-Ups   ██████████    13,100 │  │  ├─────────────────┼──────────┼───────┤│
│                   62.6%          │  │  │ NexaAI Corp     │Enterprise│$8,400 ││
│  Trial Act  ████████      8,200  │  │  │ DataPulse Inc   │Enterprise│$7,200 ││
│                   52.4%          │  │  │ CloudSync Ltd   │ Growth   │$4,100 ││
│  Activated  █████         4,300  │  │  │ Orbis Analytics │Enterprise│$3,900 ││
│                   38.1%          │  │  │ Vertex Systems  │ Growth   │$3,200 ││
│  Paid       ██            1,640  │  │  │ Apex Digital    │ Growth   │$2,800 ││
│                                  │  │  └─────────────────┴──────────┴───────┘│
│  8.9% overall visitor→paid       │  │                                        │
╰──────────────────────────────────╯  ╰────────────────────────────────────────╯

┌─ UNIT ECONOMICS & PLATFORM HEALTH ───────────────────────────────────────────┐
│                                                                               │
│  ╭─────────────────╮  ╭─────────────────╮  ╭─────────────────╮  ╭──────────────────╮
│  │ NPS Score       │  │ API Calls/Month │  │ Lifetime Value  │  │ Cust. Acq. Cost  │
│  │ 67              │  │ 48.6M           │  │ $4,320          │  │ $620             │
│  │ ▲ +4 pts MoM    │  │ ▲ +22.0% MoM    │  │ ▲ +8.1% YoY     │  │ ▼ −5.2% MoM      │
│  ╰─────────────────╯  ╰─────────────────╯  ╰─────────────────╯  ╰──────────────────╯
│                                                                               │
└───────────────────────────────────────────────────────────────────────────────┘
```

---

## KPI Summary

| Metric | Value | Change | Signal |
|--------|-------|--------|--------|
| MRR | $142,800 | +12.4% MoM | ▲ Strong |
| ARR | $1.71M | +12.4% YoY | ▲ Strong |
| Active Customers | 1,284 | +87 MoM | ▲ Strong |
| Net Churn Rate | 2.1% | −0.3% MoM | ▼ Improving |
| NPS Score | 67 | +4 pts MoM | ▲ Strong |
| API Calls / Month | 48.6M | +22.0% MoM | ▲ Strong |
| Lifetime Value (LTV) | $4,320 | +8.1% YoY | ▲ Strong |
| Customer Acq. Cost (CAC) | $620 | −5.2% MoM | ▼ Improving |
| LTV : CAC Ratio | **6.97×** | — | ✓ Healthy (>3×) |

---

## Components Used

| Widget | Type | Grid Position | Notes |
|--------|------|---------------|-------|
| MRR, ARR, Customers, Churn | `kpi` | Row 1, Col 1–12 | 4 × col-3 |
| MRR Trend | `time_series` | Row 2, Col 1–12 | Full-width line |
| Trial → Paid Funnel | `funnel` | Row 3–5, Col 1–4 | 5-stage with conversions |
| Top Customers | `table` | Row 3–5, Col 5–12 | Sorted by MRR desc |
| NPS, API, LTV, CAC | `kpi` | Row 6, Col 1–12 | 4 × col-3 |

---

## Dashboard JSON Specification

```json
{
  "dashboard": {
    "title": "NexaAI Platform — Executive KPI Dashboard",
    "filters": [
      {
        "id": "date_range",
        "type": "date_range",
        "label": "Date Range",
        "default": "last_12_months"
      },
      {
        "id": "plan_filter",
        "type": "multi_select",
        "label": "Plan",
        "field": "plan"
      }
    ],
    "widgets": [
      {
        "id": "kpi_mrr",
        "type": "kpi",
        "title": "MRR",
        "value_field": "mrr",
        "format": "currency",
        "previous_field": "mrr_prev_month",
        "comparison": "previous_period",
        "grid": { "col": 1, "row": 1, "width": 3, "height": 1 }
      },
      {
        "id": "kpi_arr",
        "type": "kpi",
        "title": "ARR",
        "value_field": "arr",
        "format": "currency",
        "previous_field": "arr_prev_year",
        "comparison": "previous_period",
        "grid": { "col": 4, "row": 1, "width": 3, "height": 1 }
      },
      {
        "id": "kpi_customers",
        "type": "kpi",
        "title": "Active Customers",
        "value_field": "active_customers",
        "format": "number_comma",
        "previous_field": "active_customers_prev_month",
        "comparison": "previous_period",
        "grid": { "col": 7, "row": 1, "width": 3, "height": 1 }
      },
      {
        "id": "kpi_churn",
        "type": "kpi",
        "title": "Net Churn Rate",
        "value_field": "net_churn_rate",
        "format": "percentage",
        "previous_field": "net_churn_rate_prev_month",
        "comparison": "previous_period",
        "grid": { "col": 10, "row": 1, "width": 3, "height": 1 }
      },
      {
        "id": "mrr_trend",
        "type": "time_series",
        "title": "MRR Trend — Last 12 Months",
        "x_field": "month",
        "y_field": "mrr",
        "x_type": "date",
        "grid": { "col": 1, "row": 2, "width": 12, "height": 2 }
      },
      {
        "id": "trial_to_paid_funnel",
        "type": "funnel",
        "title": "Trial → Paid Conversion",
        "stages": [
          { "label": "Visitors",    "value_field": "visitors" },
          { "label": "Sign-Ups",    "value_field": "signups" },
          { "label": "Trial Act",   "value_field": "trial_starts" },
          { "label": "Activated",   "value_field": "activated" },
          { "label": "Paid",        "value_field": "converted_paid" }
        ],
        "show_conversion": true,
        "show_overall": true,
        "grid": { "col": 1, "row": 4, "width": 4, "height": 3 }
      },
      {
        "id": "top_customers",
        "type": "table",
        "title": "Top Customers by MRR",
        "category_field": "company_name",
        "value_field": "mrr",
        "columns": [
          { "field": "company_name", "label": "Company" },
          { "field": "plan",         "label": "Plan" },
          { "field": "mrr",          "label": "MRR",   "format": "currency" },
          { "field": "cohort_month", "label": "Since" }
        ],
        "sort_by": "mrr",
        "sort_order": "desc",
        "grid": { "col": 5, "row": 4, "width": 8, "height": 3 }
      },
      {
        "id": "kpi_nps",
        "type": "kpi",
        "title": "NPS Score",
        "value_field": "nps_score",
        "format": "number_comma",
        "previous_field": "nps_score_prev_month",
        "comparison": "previous_period",
        "grid": { "col": 1, "row": 7, "width": 3, "height": 1 }
      },
      {
        "id": "kpi_api_calls",
        "type": "kpi",
        "title": "API Calls / Month",
        "value_field": "api_calls_monthly",
        "format": "number_comma",
        "previous_field": "api_calls_prev_month",
        "comparison": "previous_period",
        "grid": { "col": 4, "row": 7, "width": 3, "height": 1 }
      },
      {
        "id": "kpi_ltv",
        "type": "kpi",
        "title": "Customer LTV",
        "value_field": "ltv",
        "format": "currency",
        "previous_field": "ltv_prev_year",
        "comparison": "previous_period",
        "grid": { "col": 7, "row": 7, "width": 3, "height": 1 }
      },
      {
        "id": "kpi_cac",
        "type": "kpi",
        "title": "Cust. Acq. Cost",
        "value_field": "cac",
        "format": "currency",
        "previous_field": "cac_prev_month",
        "comparison": "previous_period",
        "grid": { "col": 10, "row": 7, "width": 3, "height": 1 }
      }
    ]
  }
}
```

---

## Grid Layout Map

```
Col:  1    2    3    4    5    6    7    8    9    10   11   12
      ├────────────────┼────────────────┼────────────────┼────────────────┤
R1    │     MRR  KPI   │    ARR  KPI    │  Customers KPI │  Churn KPI     │
      ├────────────────────────────────────────────────────────────────────┤
R2    │                                                                    │
R3    │                     MRR Trend (time_series)                        │
      ├─────────────────────────┬──────────────────────────────────────────┤
R4    │                         │                                          │
R5    │  Trial→Paid (funnel)    │        Top Customers (table)             │
R6    │                         │                                          │
      ├────────────────┼────────────────┼────────────────┼────────────────┤
R7    │   NPS  KPI     │  API Calls KPI │    LTV  KPI    │    CAC  KPI    │
      └────────────────┴────────────────┴────────────────┴────────────────┘
```

---

> **About the skill:** `ascii-dashboard-skill` is a Claude Code skill. Describe your dashboard in plain English and it returns:
> 1. A monospace ASCII wireframe (paste into any doc, README, or Notion page)
> 2. A JSON spec ready for implementation in Tableau, Looker, Power BI, Grafana, or React
>
> **Prompt used to generate this dashboard:**
> *"Create an executive KPI dashboard for a SaaS AI startup. Include MRR, ARR, active customers, and churn rate as headline KPIs. Show a 12-month MRR trend line. Add a trial-to-paid conversion funnel and a top customers table. Include a second row of unit economics KPIs: NPS, API calls per month, LTV, and CAC."*
