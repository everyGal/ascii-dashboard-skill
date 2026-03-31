# Component: Stream Graph

## ASCII Patterns

### Basic Stream Graph
```
╭──────────────────────────────────────────────────────────╮
│  Traffic Sources Over Time                                │
│                                                           │
│       ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░             │
│    ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░           │
│  ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓           │
│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓           │
│  ██████████████████████████████████████████████           │
│    ████████████████████████████████████████████           │
│      ████████████████████████████████████████             │
│                                                           │
│  Jan   Feb   Mar   Apr   May   Jun   Jul   Aug           │
│  ██ Direct  ▓▓ Organic  ░░ Paid                          │
╰──────────────────────────────────────────────────────────╯
```

### Stream Graph with Labels
```
╭──────────────────────────────────────────────────────────╮
│  Revenue Mix Over Time                                    │
│                                                           │
│       ░░░ SaaS ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░           │
│    ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░          │
│  ▓▓▓▓▓▓▓ Services ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓           │
│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓            │
│  ████████████ License ██████████████████████████          │
│    ████████████████████████████████████████████           │
│                                                           │
│  Q1 2023            Q1 2024            Q1 2025           │
╰──────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "stream_graph",
  "title": "(required) string — display name",
  "x_field": "(required) string — time dimension for x-axis",
  "series": [
    {
      "field": "(required) string — measure field name",
      "label": "(optional) string — legend label"
    }
  ],
  "baseline": "(optional) string — zero | silhouette | wiggle, default: wiggle",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 8-12",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 8-12 columns (needs wide canvas for flowing effect to read well)
- **Height**: 2 rows
- **Best for**: Long-running composition trends, topic/category evolution over time
- **Complexity note**: Requires centered baseline offset calculations
