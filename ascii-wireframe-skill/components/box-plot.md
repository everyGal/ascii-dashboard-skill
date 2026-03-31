# Component: Box Plot

## ASCII Patterns

### Basic Box Plot
```
╭──────────────────────────────────────╮
│ Salary Distribution by Department    │
│                                      │
│  120K ┤                              │
│       │        ┬                     │
│  100K ┤   ┬    │                     │
│       │   │   ┌┤                     │
│   80K ┤  ┌┤   ├┤    ┬               │
│       │  ├┤   └┤    │               │
│   60K ┤  └┤    ┴   ┌┤               │
│       │   ┴        ├┤    ┬          │
│   40K ┤            └┤   ┌┤          │
│       │             ┴   ├┤          │
│   20K ┤                 └┤          │
│       │                  ┴          │
│    0K ┼──┴───┴───┴───┴──           │
│       Eng  Sales  Mkt   Ops        │
╰──────────────────────────────────────╯
```

### Box Plot with Outliers
```
╭──────────────────────────────────────╮
│ Response Time by Service (ms)        │
│                                      │
│  500 ┤            ○                  │
│      │                               │
│  400 ┤   ○                           │
│      │                               │
│  300 ┤   ┬        ┬                  │
│      │  ┌┤       ┌┤       ┬         │
│  200 ┤  ├┤       ├┤      ┌┤         │
│      │  └┤       └┤      ├┤         │
│  100 ┤   ┴        ┴      └┤         │
│      │                     ┴         │
│    0 ┼──┴────────┴────────┴──       │
│      Auth     Search    Cache       │
│                                      │
│  ┌┤ IQR  ─ Median  ○ Outlier       │
╰──────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "box_plot",
  "title": "(required) string — display name",
  "category_field": "(required) string — dimension for each box (department, service, etc.)",
  "value_field": "(required) string — continuous measure to compute distribution",
  "show_outliers": "(optional) bool — display outlier points, default: true",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 5-6",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 5-6 columns (needs enough space for multiple box plots side by side)
- **Height**: 2 rows
- **Common pattern**: Paired with a histogram (6+6), or single at 8 columns for detailed view
