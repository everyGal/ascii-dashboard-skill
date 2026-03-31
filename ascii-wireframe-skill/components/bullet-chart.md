# Component: Bullet Chart

## ASCII Patterns

### Basic Bullet Chart
```
╭──────────────────────────────────────────╮
│  Q4 Sales Performance                    │
│                                          │
│  Revenue                                 │
│  ░░░░░░░░░░░░░░░████████████▲░░░         │
│  $0         $50K    $80K Target $100K    │
│                                          │
│  Units Sold                              │
│  ░░░░░░░░░░░░████████████████░░░░        │
│   0         500    800  Target 1000      │
│                                          │
│  Win Rate                                │
│  ░░░░░░░░░░░░░░░████████████▲░░          │
│  0%          20%    32%   Target 35%     │
╰──────────────────────────────────────────╯
```

### Horizontal Bullet Array
```
╭──────────────────────────────────────────╮
│  Regional Targets                        │
│                                          │
│  North  ░░░░░░██████████████▲░░░░  92%  │
│  South  ░░░░░░░░████████████░░░░░  78%  │
│  East   ░░░░░░░░░████████████▲░░░  88%  │
│  West   ░░░░░░░█████████████████  105%  │
│                                          │
│  ░ Background  █ Actual  ▲ Target       │
╰──────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "bullet_chart",
  "title": "(required) string — display name",
  "category_field": "(required) string — dimension for each bullet row",
  "value_field": "(required) string — actual measure value",
  "target_field": "(required) string — target/goal measure value",
  "max_field": "(optional) string — max range value (for background bar)",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 6-8 columns (horizontal layout needs space for labels + bar + value)
- **Height**: 2 rows
- **Best for**: Actual vs. target comparisons, performance scorecards, KPI with benchmarks
