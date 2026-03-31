# Component: Line Chart

## ASCII Patterns

### Single Line
```
╭──────────────────────────────────────╮
│ Monthly Revenue                       │
│                                       │
│  100 ┤              ╱──╲              │
│   80 ┤         ╱──╱     ╲──╱╲        │
│   60 ┤    ╱──╱                ╲      │
│   40 ┤  ╱                      ╲     │
│   20 ┤╱                              │
│    0 ┼──┬──┬──┬──┬──┬──┬──┬──┬──     │
│       J  F  M  A  M  J  J  A  S      │
╰──────────────────────────────────────╯
```

### Multi-Series Line
```
╭──────────────────────────────────────╮
│ Revenue by Channel                    │
│                                       │
│  100 ┤              ╱──╲  ── Online   │
│   80 ┤         ╱──╱     ╲  ╌╌ Retail  │
│   60 ┤    ╱──╱      ╌╌╌╌╌╌╌╌╌       │
│   40 ┤  ╱      ╌╌╌╌╌                 │
│   20 ┤╱   ╌╌╌╌                       │
│    0 ┼──┬──┬──┬──┬──┬──┬──┬──┬──     │
│       J  F  M  A  M  J  J  A  S      │
╰──────────────────────────────────────╯
```

### Time-Series Line
```
╭──────────────────────────────────────╮
│ Daily Active Users (2024)             │
│                                       │
│  5K  ┤           ╱╲    ╱╲            │
│  4K  ┤     ╱╲  ╱    ╲╱    ╲╱╲       │
│  3K  ┤   ╱    ╱                ╲     │
│  2K  ┤ ╱╱                       ╲    │
│  1K  ┤╱                              │
│   0  ┼──┬──┬──┬──┬──┬──┬──┬──┬──    │
│      Jan  Mar  May  Jul  Sep  Nov    │
╰──────────────────────────────────────╯
```

## Spec Template

### Single Line
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "line",
  "title": "(required) string — display name",
  "x_field": "(required) string — dimension field for x-axis",
  "y_field": "(required) string — measure field for y-axis",
  "x_type": "(optional) string | date — default: string",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 5-8",
    "height": "(required) int — typically 2"
  }
}
```

### Multi-Series Line
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "multi_series",
  "title": "(required) string — display name",
  "x_field": "(required) string — shared x-axis field",
  "x_type": "(optional) string | date — default: string",
  "series": ["Revenue", "Cost", "Profit"],
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2"
  }
}
```

### Time-Series Line
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "time_series",
  "title": "(required) string — display name",
  "x_field": "(required) string — date field for x-axis",
  "y_field": "(required) string — measure field for y-axis",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 5-8 columns (use 6 for side-by-side, 8 or 12 for featured trends)
- **Height**: 2 rows
- **Common pattern**: Full-width time-series (12 cols) below KPI row, or paired with bar chart (6+6)
