# Component: Combo Chart

## ASCII Patterns

### Bar + Line Combo
```
╭──────────────────────────────────────╮
│ Revenue vs Profit Margin              │
│                                       │
│  120 ┤           ╱──╲          30%   │
│  100 ┤  ██  ╱──╱     ╲──╲     25%   │
│   80 ┤  ██  ██            ╲   20%   │
│   60 ┤  ██  ██  ██            15%   │
│   40 ┤  ██  ██  ██  ██  ██   10%   │
│   20 ┤  ██  ██  ██  ██  ██    5%   │
│    0 ┼──┴───┴───┴───┴───┴──    0%   │
│       Q1   Q2   Q3   Q4   Q5        │
│       ██ Revenue  ── Margin %        │
╰──────────────────────────────────────╯
```

### Bar + Line (monthly trend)
```
╭──────────────────────────────────────────────────╮
│ Sales Volume & Conversion Rate                    │
│                                                   │
│  500 ┤                 ╱╲                   8%   │
│  400 ┤     ╱╲    ╱──╱    ╲──╱╲             6%   │
│  300 ┤  ██╱  ╲╱██              ╲──         4%   │
│  200 ┤  ██  ██  ██  ██  ██  ██  ██  ██    2%   │
│  100 ┤  ██  ██  ██  ██  ██  ██  ██  ██    1%   │
│    0 ┼──┴───┴───┴───┴───┴───┴───┴───┴──    0%   │
│       Jan  Feb  Mar  Apr  May  Jun  Jul  Aug     │
│       ██ Sales Volume   ── Conversion Rate       │
╰──────────────────────────────────────────────────╯
```

### Bar + Line (dual axis emphasis)
```
╭──────────────────────────────────────╮
│ Headcount & Cost per Hire             │
│                                       │
│   50 ┤              ╱──╲       $12K  │
│   40 ┤  ██     ╱──╱     ╲     $10K  │
│   30 ┤  ██  ██╱            ╲   $8K  │
│   20 ┤  ██  ██  ██  ██         $6K  │
│   10 ┤  ██  ██  ██  ██  ██    $4K  │
│    0 ┼──┴───┴───┴───┴───┴──   $0K  │
│       Q1   Q2   Q3   Q4   Q5        │
│       ██ Hires   ── Cost/Hire        │
╰──────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "combo",
  "title": "(required) string — display name",
  "x_field": "(required) string — shared x-axis dimension field",
  "combo": {
    "primary_field": "(required) string — measure for primary axis (bars)",
    "secondary_field": "(required) string — measure for secondary axis (line)",
    "primary_type": "(optional) bar | line — default: bar",
    "secondary_type": "(optional) bar | line — default: line"
  },
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 6-8 columns (use 6 for side-by-side with another chart, 8 or 12 for featured)
- **Height**: 2 rows
- **Common pattern**: Full-width combo chart (12 cols) showing a volume metric (bars) against a rate metric (line), or paired with a KPI row above
- **Best practice**: Use bars for absolute values (revenue, count) and line for rates/percentages (margin, conversion rate) to leverage dual axes effectively
