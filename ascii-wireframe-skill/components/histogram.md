# Component: Histogram

## ASCII Patterns

### Basic Histogram
```
╭──────────────────────────────────────╮
│ Deal Size Distribution                │
│                                       │
│   80 ┤        ██                      │
│   60 ┤     ████                       │
│   40 ┤  ████████                      │
│   20 ┤██████████████                  │
│   10 ┤████████████████████            │
│    0 ┼──┴──┴──┴──┴──┴──┴──           │
│      0  10  20  30  40  50  60+      │
│             Deal Size ($K)            │
╰──────────────────────────────────────╯
```

### Histogram with Normal Curve
```
╭──────────────────────────────────────╮
│ Response Time Distribution (ms)      │
│                                       │
│   90 ┤         ╭──╮                  │
│   70 ┤        ╱    ╲                 │
│   50 ┤  ██   ╱  ██  ╲   ██          │
│   30 ┤  ████╱████████╲████           │
│   10 ┤███████████████████████        │
│    0 ┼──┴──┴──┴──┴──┴──┴──┴──       │
│       50  100 150 200 250 300 350    │
│                                       │
│   ── Normal distribution curve       │
╰──────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "histogram",
  "title": "(required) string — display name",
  "value_field": "(required) string — continuous measure to bin",
  "bin_count": "(optional) int — number of bins, default: auto",
  "bin_size": "(optional) number — fixed bin width (overrides bin_count)",
  "show_curve": "(optional) bool — overlay normal distribution curve, default: false",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 5-6",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 5-6 columns
- **Height**: 2 rows
- **Best for**: Showing distribution of a single continuous measure (deal sizes, response times, order values)
- **Common pattern**: Paired with a box plot or scatter (6+6)
