# Component: Gauge

## ASCII Patterns

### Basic Gauge
```
╭──────────────────────────────────────────╮
│  Customer Satisfaction Score             │
│                                          │
│              ╭─────────╮                 │
│           ╭──┤░░░▓▓▓███├──╮              │
│         ╭─┤░░│░░░▓▓▓███│██├─╮            │
│        │░░░░░│░░░▓▓▓███│████│            │
│        │░░░░░│░░░▓▓▓███│████│            │
│         ╰──┤░░░░▓▓▓▓███├──╯             │
│             ╰────╲─────╯                 │
│                   ╲                      │
│                  78%                     │
│                                          │
│  ░░░ Poor    ▓▓▓ Fair     ███ Good       │
│  (0-40)      (40-70)     (70-100)        │
╰──────────────────────────────────────────╯
```

### Compact Gauge with Target
```
╭──────────────────────────────────────────╮
│  SLA Compliance                          │
│                                          │
│            ╭───────────╮                 │
│          ╭─┤░░░░▓▓█████├─╮               │
│         │░░░░░░▓▓██████▲██│              │
│          ╰─┤░░░░▓▓█████├─╯               │
│            ╰─────┼─────╯                 │
│                  │                       │
│               92.4%                      │
│          Target: 95% ▲                   │
│                                          │
╰──────────────────────────────────────────╯
```

### Multiple Mini Gauges
```
╭──────────────────────────────────────────╮
│  System Health                           │
│                                          │
│   ╭─────╮    ╭─────╮    ╭─────╮          │
│   │░▓███│    │░▓███│    │░▓███│          │
│   ╰──┼──╯    ╰──┼──╯    ╰──┼──╯          │
│    CPU 72%   Mem 84%   Disk 45%          │
│                                          │
╰──────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string",
  "type": "gauge",
  "title": "(required) string",
  "value_field": "(required) string — current value metric",
  "min_value": "(optional) number — scale minimum, default: 0",
  "max_value": "(optional) number — scale maximum, default: 100",
  "target_value": "(optional) number — target marker value",
  "target_field": "(optional) string — field for dynamic target",
  "zones": [
    {
      "label": "(optional) string — zone label",
      "threshold": "(required) number — upper bound of this zone"
    }
  ],
  "format": "(optional) string — number format, e.g. '0.0%' or '#,##0'",
  "grid": {
    "col": "(required) int",
    "row": "(required) int",
    "width": "(required) int — typically 3-4",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 3-4 columns
- **Height**: 2 rows
- **Best for**: Single-metric health indicators, SLA compliance, performance scores
