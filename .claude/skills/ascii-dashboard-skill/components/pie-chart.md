# Component: Pie Chart

## ASCII Patterns

### Pie Chart
```
╭──────────────────────────────╮
│ Revenue by Segment            │
│                               │
│         ██████████            │
│       ██████████████          │
│      ████████████████         │
│      ████████████████         │
│       ██████████████          │
│         ██████████            │
│                               │
│  ◉ Enterprise    42%          │
│  ◉ Mid-Market    28%          │
│  ◉ SMB           19%          │
│  ◉ Startup       11%          │
╰──────────────────────────────╯
```

### Pie Chart (fewer segments)
```
╭──────────────────────────────╮
│ Market Share                  │
│                               │
│         ██████████            │
│       ██████████████          │
│      ████████████████         │
│      ████████████████         │
│       ██████████████          │
│         ██████████            │
│                               │
│  ◉ Our Product    58%         │
│  ◉ Competitor A   27%         │
│  ◉ Others         15%         │
╰──────────────────────────────╯
```

### Donut Chart
```
╭──────────────────────────────╮
│ Budget Allocation             │
│                               │
│         ██████████            │
│       ████      ████          │
│      ███          ███         │
│      ███   $2.4M  ███        │
│      ███          ███         │
│       ████      ████          │
│         ██████████            │
│                               │
│  ◉ Engineering   45%          │
│  ◉ Marketing     30%          │
│  ◉ Operations    25%          │
╰──────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "pie",
  "title": "(required) string — display name",
  "category_field": "(required) string — dimension field for slices",
  "value_field": "(required) string — measure field for slice size",
  "variant": "(optional) pie | donut — default: pie",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 4-5",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 4-5 columns (use 4 for side-by-side with other charts, 5 for slightly more room)
- **Height**: 2 rows
- **Common pattern**: Paired with a bar chart or table (4+8 or 5+7), or two pie charts side-by-side (6+6)
- **Best practice**: Limit to 5-7 segments; use sparingly as bar charts are often more readable
