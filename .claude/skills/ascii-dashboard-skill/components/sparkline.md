# Component: Sparkline

## ASCII Patterns

### Inline Sparklines in a KPI Row
```
╭──────────────────────────────────────────────────────────────╮
│  KPI Metrics with Trend                                      │
│                                                              │
│  ╭───────────────────╮  ╭───────────────────╮               │
│  │ Revenue    $1.2M  │  │ Users    45,200   │               │
│  │ ▲ 12.5%           │  │ ▲ 8.3%            │               │
│  │ ╱╲  ╱╲╱╲╱╲       │  │  ╱╲╱╲╱╲╱╲        │               │
│  ╰───────────────────╯  ╰───────────────────╯               │
╰──────────────────────────────────────────────────────────────╯
```

### Sparkline Table
```
╭────────────────────────────────────────────────────────╮
│  Product Trends                                        │
│                                                        │
│  Product      Revenue   Trend (12wk)     Change       │
│  ─────────────────────────────────────────────        │
│  Widget A     $142K     ╱╲╱╲╱╲╱╲╱╲      ▲ 12%        │
│  Widget B     $108K      ╲╱╲╱╲╱╲         ▼  3%        │
│  Widget C      $87K     ╱╲╱╲╱╲╱╲╱╲      ▲  8%        │
│  Widget D      $62K        ╲╱╲╱╲╱         ▼  7%       │
│  Widget E      $41K     ╱╲╱╲  ╱╲╱        ▲ 21%        │
╰────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "sparkline",
  "title": "(required) string — display name",
  "x_field": "(required) string — time/sequence dimension",
  "y_field": "(required) string — measure to plot",
  "category_field": "(optional) string — dimension for multiple sparklines in a table",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 2-4",
    "height": "(required) int — typically 1"
  }
}
```

## Sizing Guidelines
- **Width**: 2-4 columns (typically embedded in KPI cards or table columns)
- **Height**: 1 row
- **Best for**: Trend indicator alongside a KPI, small multiples for comparing trends across categories
