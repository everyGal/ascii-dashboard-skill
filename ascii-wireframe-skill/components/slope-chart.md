# Component: Slope Chart

## ASCII Patterns

### Basic Slope Chart
```
╭──────────────────────────────────────╮
│ Market Share: 2024 vs 2025           │
│                                      │
│   2024              2025             │
│                                      │
│   38% ── Brand A ─────── 42%        │
│   29% ── Brand B ──╲     31%        │
│   18% ── Brand C ───╲──╱ 15%        │
│   10% ── Brand D ────── 08%         │
│    5% ── Brand E ─────── 04%        │
╰──────────────────────────────────────╯
```

### Slope Chart with Diverging Trends
```
╭──────────────────────────────────────╮
│ Employee Engagement Score            │
│                                      │
│   H1 2025           H2 2025          │
│                                      │
│   88 ── Engineering ──╱── 92         │
│   82 ── Product ──────── 84         │
│   79 ── Design ───╱───── 86         │
│   75 ── Sales ────╲───── 68         │
│   71 ── Support ──╲──── 65          │
│                                      │
│   ╱ Improved  ── Stable  ╲ Declined │
╰──────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "slope_chart",
  "title": "(required) string — display name",
  "category_field": "(required) string — dimension for each line (brand, team, etc.)",
  "start_value_field": "(required) string — measure for left column value",
  "end_value_field": "(required) string — measure for right column value",
  "start_label": "(optional) string — label for left column, e.g. '2024'",
  "end_label": "(optional) string — label for right column, e.g. '2025'",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 4-5",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 4-5 columns (compact by nature — only two data columns)
- **Height**: 2 rows
- **Common pattern**: Paired with a KPI row above (4 columns), or side-by-side with a bar chart for context (5+7)
