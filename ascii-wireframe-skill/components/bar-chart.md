# Component: Bar Chart

## ASCII Patterns

### Vertical Bar
```
╭──────────────────────────────────────╮
│ Revenue by Region                     │
│                                       │
│  120 ┤                                │
│  100 ┤  ██                            │
│   80 ┤  ██  ██                        │
│   60 ┤  ██  ██  ██                    │
│   40 ┤  ██  ██  ██  ██               │
│   20 ┤  ██  ██  ██  ██  ██           │
│    0 ┼──┴───┴───┴───┴───┴──          │
│       NA   EU  APAC  LA  MEA         │
╰──────────────────────────────────────╯
```

### Horizontal Bar
```
╭──────────────────────────────────────╮
│ Top Products                          │
│                                       │
│  Product A  ████████████████  $142K   │
│  Product B  ████████████      $108K   │
│  Product C  █████████         $87K    │
│  Product D  ██████            $62K    │
│  Product E  ████              $41K    │
╰──────────────────────────────────────╯
```

### Stacked Bar
```
╭──────────────────────────────────────╮
│ Revenue by Region & Category          │
│                                       │
│  120 ┤                                │
│  100 ┤  ▓▓                            │
│   80 ┤  ██  ▓▓                        │
│   60 ┤  ██  ██  ▓▓                    │
│   40 ┤  ██  ██  ██  ▓▓               │
│   20 ┤  ██  ██  ██  ██               │
│    0 ┼──┴───┴───┴───┴──              │
│       Q1   Q2   Q3   Q4              │
│       ██ Online  ▓▓ In-Store         │
╰──────────────────────────────────────╯
```

### Grouped Bar
```
╭──────────────────────────────────────╮
│ Sales: Actual vs Target               │
│                                       │
│  100 ┤                                │
│   80 ┤  ██▓▓          ██▓▓           │
│   60 ┤  ██▓▓  ██▓▓    ██▓▓           │
│   40 ┤  ██▓▓  ██▓▓    ██▓▓  ██▓▓    │
│   20 ┤  ██▓▓  ██▓▓    ██▓▓  ██▓▓    │
│    0 ┼──┴──────┴───────┴──────┴──    │
│       Q1      Q2      Q3      Q4     │
│       ██ Actual  ▓▓ Target           │
╰──────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "bar",
  "title": "(required) string — display name",
  "category_field": "(required) string — dimension field for categories",
  "value_field": "(required) string — measure field for bar height/length",
  "horizontal": "(optional) bool — true for horizontal bars, default: false",
  "variant": "(optional) standard | stacked | grouped — default: standard",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 4-6",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 4-6 columns (use 4 for side-by-side charts, 6 for featured)
- **Height**: 2 rows
- **Common pattern**: Two bar charts side-by-side (6+6 or 4+8), or single full-width (12)
