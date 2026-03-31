# Component: KPI Card

## ASCII Patterns

### Single KPI
```
╭───────────╮
│ Revenue    │
│ $1.2M      │
╰───────────╯
```

### KPI with Delta
```
╭───────────╮
│ Revenue    │
│ $1.2M      │
│ ▲ 12.5%    │
╰───────────╯
```

### KPI with Subtitle
```
╭───────────╮
│ Revenue    │
│ $1.2M      │
│ vs $1.1M   │
╰───────────╯
```

### KPI Row (typical usage)
```
╭───────────╮  ╭───────────╮  ╭───────────╮  ╭───────────╮
│ Revenue    │  │ Users      │  │ Conv Rate  │  │ Avg Order  │
│ $1.2M      │  │ 45,200     │  │ 3.8%       │  │ $67.50     │
│ ▲ 12.5%    │  │ ▲ 8.3%     │  │ ▼ 0.4%     │  │ ▲ 2.1%     │
╰───────────╯  ╰───────────╯  ╰───────────╯  ╰───────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "kpi",
  "title": "(required) string — display name",
  "value_field": "(required) string — primary metric field name",
  "format": "(optional) number_comma | percentage | currency | decimal — default: number_comma",
  "previous_field": "(optional) string — field for comparison value",
  "comparison": "(optional) previous_period | target — comparison type",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 2-3",
    "height": "(required) int — typically 1"
  }
}
```

## Sizing Guidelines
- **Width**: 2-3 columns (use 2 for 5-6 KPIs in a row, 3 for 4 KPIs)
- **Height**: 1 row
- **Common pattern**: Row of 3-6 KPI cards spanning full width (row 1)
