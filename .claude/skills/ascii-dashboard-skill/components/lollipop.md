# Component: Lollipop Chart

## ASCII Patterns

### Horizontal Lollipop
```
╭──────────────────────────────────────╮
│ Customer Satisfaction by Channel     │
│                                      │
│  Live Chat  ─────────────────── ● 92 │
│  Phone      ──────────────── ●    85 │
│  Email      ────────────── ●      78 │
│  Social     ────────── ●          64 │
│  Self-Serve ──────── ●            58 │
╰──────────────────────────────────────╯
```

### Lollipop with Target Line
```
╭──────────────────────────────────────╮
│ Q4 Sales vs Target ($K)              │
│                                      │
│                          Target │    │
│                             ┊   │    │
│  Region A  ─────────────── ●┊   │    │
│  Region B  ──────────────────── ●    │
│  Region C  ────────── ●    ┊        │
│  Region D  ──────────────● ┊        │
│  Region E  ────── ●       ┊         │
│                            ┊         │
│             0   20  40  60  80  100  │
╰──────────────────────────────────────╯
```

### Vertical Lollipop
```
╭──────────────────────────────────────╮
│ Monthly Signups (K)                  │
│                                      │
│  12 ┤           ●                    │
│  10 ┤     ●     │     ●             │
│   8 ┤  ●  │  ●  │  ●  │             │
│   6 ┤  │  │  │  │  │  │  ●          │
│   4 ┤  │  │  │  │  │  │  │          │
│   2 ┤  │  │  │  │  │  │  │          │
│   0 ┼──┴──┴──┴──┴──┴──┴──┴──       │
│      Jan Feb Mar Apr May Jun Jul    │
╰──────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "lollipop",
  "title": "(required) string — display name",
  "category_field": "(required) string — dimension for each lollipop",
  "value_field": "(required) string — measure controlling stem length",
  "horizontal": "(optional) bool — true for horizontal layout, default: true",
  "target_value": "(optional) number — reference line value for target/benchmark",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 4-6",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 4-6 columns (similar to bar chart)
- **Height**: 2 rows
- **Common pattern**: Side-by-side with a bar chart (6+6) for comparison, or standalone at 6 columns as a cleaner alternative to bars
