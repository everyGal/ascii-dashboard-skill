# Layout: Operations Overview Dashboard

## Prompt

"Operations dashboard with throughput, defect rate, uptime, MTTR KPIs, a Gantt chart for project timeline, a heatmap of incidents by hour/day, and a gauge for SLA compliance."

## ASCII Wireframe

```
╔══════════════════════════════════════════════════════════════════════════════════════════════╗
║  Operations Overview                                      [Team ▾] [Date Range ▾]           ║
╠══════════════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                              ║
║  ╭─────────────╮  ╭─────────────╮  ╭─────────────╮  ╭─────────────╮                         ║
║  │ Throughput  │  │ Defect Rate │  │   Uptime    │  │    MTTR     │                         ║
║  │  12,450     │  │   0.82%     │  │  99.94%     │  │  23 min     │                         ║
║  │  units/day  │  │  ▼ 0.15pp   │  │  ▲ 0.02pp   │  │  ▼ 8 min    │                         ║
║  │  ▲ 4.2%     │  │  (improved) │  │  (improved) │  │  (improved) │                         ║
║  ╰─────────────╯  ╰─────────────╯  ╰─────────────╯  ╰─────────────╯                         ║
║                                                                                              ║
║  ╭──────────────────────────────────────────────────────╮  ╭────────────────────╮            ║
║  │ Project Timeline (Gantt)                             │  │ SLA Compliance     │            ║
║  │                                                      │  │ (Gauge)            │            ║
║  │  Project      Jan    Feb    Mar    Apr    May         │  │                    │            ║
║  │  ────────────────────────────────────────────         │  │     ╭─────╮        │            ║
║  │  Platform v2  ███████████████                        │  │   ╱    97.2%╲      │            ║
║  │  API Rebuild         ████████████████                │  │  ╱           ╲     │            ║
║  │  Data Migration            ████████████              │  │ ║  ╭───╮      ║    │            ║
║  │  Security Audit                  ███████             │  │ ║  │ ▲ │      ║    │            ║
║  │  Mobile App     ██████████████████████████████       │  │  ╲ ╰───╯     ╱     │            ║
║  │  Infra Upgrade        ████████████                   │  │   ╲         ╱      │            ║
║  │                                                      │  │     ╰─────╯        │            ║
║  │  ███ On Track  ░░░ At Risk  ▓▓▓ Complete             │  │  Target: 99.5%     │            ║
║  ╰──────────────────────────────────────────────────────╯  ╰────────────────────╯            ║
║                                                                                              ║
║  ╭──────────────────────────────────╮  ╭──────────────────────────────────╮                  ║
║  │ Incident Heatmap (Hour x Day)   │  │ Incident Log                     │                  ║
║  │                                  │  │                                   │                  ║
║  │       00  04  08  12  16  20     │  │  Time     │ Severity│ Service     │                  ║
║  │  Mon  ░░  ░░  ▒▒  ██  ▒▒  ░░    │  │  ─────────┼─────────┼──────────── │                  ║
║  │  Tue  ░░  ░░  ▒▒  ▒▒  ▒▒  ░░    │  │  14:32    │ P1      │ API Gateway │                  ║
║  │  Wed  ░░  ░░  ░░  ▒▒  ██  ▒▒    │  │  09:15    │ P2      │ Database    │                  ║
║  │  Thu  ░░  ▒▒  ▒▒  ██  ██  ▒▒    │  │  22:47    │ P3      │ CDN         │                  ║
║  │  Fri  ░░  ░░  ██  ██  ▒▒  ░░    │  │  11:03    │ P2      │ Auth Svc    │                  ║
║  │  Sat  ░░  ░░  ░░  ░░  ░░  ░░    │  │  03:28    │ P1      │ Queue       │                  ║
║  │  Sun  ░░  ░░  ░░  ░░  ░░  ░░    │  │  16:55    │ P3      │ Storage     │                  ║
║  │                                  │  │                                   │                  ║
║  │  ░░ Low  ▒▒ Medium  ██ High     │  │                                   │                  ║
║  ╰──────────────────────────────────╯  ╰──────────────────────────────────╯                  ║
║                                                                                              ║
╚══════════════════════════════════════════════════════════════════════════════════════════════╝
```

## JSON Spec

```json
{
  "dashboard": {
    "title": "Operations Overview",
    "layout": {
      "columns": 12,
      "rows": "auto"
    },
    "filters": [
      {
        "field": "Team",
        "type": "dropdown",
        "default": "All"
      },
      {
        "field": "Date",
        "type": "date_range",
        "default": "Last 30 Days"
      }
    ],
    "widgets": [
      {
        "id": "kpi_throughput",
        "type": "kpi",
        "title": "Throughput",
        "grid": { "col": 1, "row": 1, "width": 3, "height": 1 },
        "value_field": "Throughput",
        "previous_field": "Previous Throughput",
        "comparison": "percent_change",
        "format": "number",
        "subtitle": "units/day"
      },
      {
        "id": "kpi_defect_rate",
        "type": "kpi",
        "title": "Defect Rate",
        "grid": { "col": 4, "row": 1, "width": 3, "height": 1 },
        "value_field": "Defect Rate",
        "previous_field": "Previous Defect Rate",
        "comparison": "absolute_change",
        "format": "percent",
        "subtitle": "improved"
      },
      {
        "id": "kpi_uptime",
        "type": "kpi",
        "title": "Uptime",
        "grid": { "col": 7, "row": 1, "width": 3, "height": 1 },
        "value_field": "Uptime",
        "previous_field": "Previous Uptime",
        "comparison": "absolute_change",
        "format": "percent",
        "subtitle": "improved"
      },
      {
        "id": "kpi_mttr",
        "type": "kpi",
        "title": "MTTR",
        "grid": { "col": 10, "row": 1, "width": 3, "height": 1 },
        "value_field": "MTTR",
        "previous_field": "Previous MTTR",
        "comparison": "absolute_change",
        "format": "number",
        "subtitle": "minutes, improved"
      },
      {
        "id": "project_gantt",
        "type": "gantt",
        "title": "Project Timeline",
        "grid": { "col": 1, "row": 2, "width": 8, "height": 2 },
        "category_field": "Project",
        "start_field": "Start Date",
        "end_field": "End Date",
        "color_field": "Status"
      },
      {
        "id": "sla_gauge",
        "type": "gauge",
        "title": "SLA Compliance",
        "grid": { "col": 9, "row": 2, "width": 4, "height": 2 },
        "value_field": "SLA Compliance",
        "target_field": "SLA Target",
        "min_value": 0,
        "max_value": 100,
        "format": "percent"
      },
      {
        "id": "incident_heatmap",
        "type": "heatmap",
        "title": "Incident Heatmap",
        "grid": { "col": 1, "row": 4, "width": 6, "height": 2 },
        "x_field": "Hour",
        "y_field": "Day of Week",
        "value_field": "Incident Count",
        "color_scale": "sequential"
      },
      {
        "id": "incident_log_table",
        "type": "table",
        "title": "Incident Log",
        "grid": { "col": 7, "row": 4, "width": 6, "height": 2 },
        "category_field": "Time",
        "value_field": "Severity",
        "columns": ["Time", "Severity", "Service", "Description", "Status", "Resolution"]
      }
    ]
  }
}
```

## Notes

- The 4 KPIs use width 3 each, filling the full 12-column row. Defect Rate and MTTR use inverted comparison (lower is better).
- Row 2-3 splits 8:4 for the Gantt chart and gauge.
- Row 4-5 splits 6:6 for the heatmap and incident log table.
