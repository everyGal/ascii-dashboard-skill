# Component: Area Chart

## ASCII Patterns

### Single Area
```
╭──────────────────────────────────────╮
│ Cumulative Revenue                    │
│                                       │
│  100 ┤              ╱──╲              │
│   80 ┤         ╱──╱█████╲            │
│   60 ┤    ╱──╱████████████╲          │
│   40 ┤  ╱█████████████████████       │
│   20 ┤╱███████████████████████       │
│    0 ┼████████████████████████       │
│       J  F  M  A  M  J  J  A  S      │
╰──────────────────────────────────────╯
```

### Stacked Area
```
╭──────────────────────────────────────╮
│ Traffic Sources Over Time             │
│                                       │
│  100 ┤▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓       │
│   80 ┤▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓       │
│   60 ┤████▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓       │
│   40 ┤██████████████████████▓▓       │
│   20 ┤░░░░████████████████████       │
│    0 ┼░░░░░░░░░░░░████████████       │
│       J  F  M  A  M  J  J  A         │
│       █ Direct  ▓ Organic  ░ Paid    │
╰──────────────────────────────────────╯
```

### Stacked Area (multiple series)
```
╭──────────────────────────────────────╮
│ Revenue by Product Line               │
│                                       │
│  250 ┤              ▓▓▓▓▓▓▓▓▓        │
│  200 ┤         ▓▓▓▓▓▓▓▓▓▓▓▓▓▓       │
│  150 ┤    ▓▓▓▓▓████████████▓▓▓      │
│  100 ┤  ▓▓████████████████████       │
│   50 ┤░░██████████████████████       │
│    0 ┼░░░░░░░░████████████████       │
│       Q1    Q2    Q3    Q4            │
│       █ Enterprise  ▓ SMB  ░ Free    │
╰──────────────────────────────────────╯
```

## Spec Template

### Single Area
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "area",
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

### Stacked Area
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "area",
  "title": "(required) string — display name",
  "x_field": "(required) string — shared x-axis field",
  "x_type": "(optional) string | date — default: string",
  "series": [
    {
      "field": "(required) string — measure field name",
      "label": "(optional) string — legend label"
    }
  ],
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 5-8 columns (use 6 for side-by-side, 8 or 12 for full-width trends)
- **Height**: 2 rows
- **Common pattern**: Full-width stacked area (12 cols) to show composition over time, or paired with line chart (6+6)
