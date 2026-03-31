# Component: Heatmap

## ASCII Patterns

### Category x Category Heatmap
```
╭──────────────────────────────────────────────────╮
│ Sales by Region & Category                        │
│                                                   │
│          Electronics  Apparel  Food  Software     │
│  North       ██           ▓▓     ░░     ██        │
│  South       ▓▓           ██     ▓▓     ░░        │
│  East        ░░           ▓▓     ██     ▓▓        │
│  West        ██           ░░     ▓▓     ██        │
│  Central     ▓▓           ██     ░░     ▓▓        │
│                                                   │
│  ░░ Low   ▓▓ Medium   ██ High                    │
╰──────────────────────────────────────────────────╯
```

### Correlation Heatmap
```
╭──────────────────────────────────────────────────╮
│ Metric Correlation Matrix                         │
│                                                   │
│           Rev   Cost  Margin  Volume  NPS         │
│  Rev       ██    ▓▓     ▓▓      ██     ░░         │
│  Cost      ▓▓    ██     ░░      ▓▓     ░░         │
│  Margin    ▓▓    ░░     ██      ░░     ██         │
│  Volume    ██    ▓▓     ░░      ██     ░░         │
│  NPS       ░░    ░░     ██      ░░     ██         │
│                                                   │
│  ░░ Low   ▓▓ Medium   ██ High correlation        │
╰──────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "heatmap",
  "title": "(required) string — display name",
  "x_field": "(required) string — dimension for columns",
  "y_field": "(required) string — dimension for rows",
  "value_field": "(required) string — measure controlling color intensity",
  "color_scale": "(optional) sequential | diverging — default: sequential",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 6-8 columns (needs room for both row and column labels)
- **Height**: 2 rows
- **Common pattern**: Paired with a table or bar chart (6+6)
