# Component: Filter Bar

## ASCII Patterns

### Basic Filter Bar
```
╭─────────────────────────────────────────────────────────╮
│  [Date Range ▾]  [Region ▾]  [Product ▾]  [Reset]       │
╰─────────────────────────────────────────────────────────╯
```

### Filter Bar with Search
```
╭─────────────────────────────────────────────────────────╮
│  🔍 Search...  [Quarter ▾]  [Team ▾]  [Status ▾]        │
╰─────────────────────────────────────────────────────────╯
```

### Inline Dashboard Header with Filters
```
╔═════════════════════════════════════════════════════════╗
║  Sales Dashboard          [Quarter ▾]  [Rep ▾]  [🔄]   ║
╚═════════════════════════════════════════════════════════╝
```

### Multi-Row Filter Bar
```
╭─────────────────────────────────────────────────────────╮
│  Date:  [Last 30 days ▾]   Region:  [All ▾]             │
│  Stage: [All ▾]            Rep:     [All ▾]              │
╰─────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "filter_bar",
  "title": "(optional) string — filter section label",
  "filters": [
    {
      "field": "(required) string — data field to filter on",
      "label": "(required) string — display label",
      "control": "(optional) dropdown | date_range | slider | search — default: dropdown",
      "default": "(optional) string — default value"
    }
  ],
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 12 (full width)",
    "height": "(required) int — typically 1"
  }
}
```

## Sizing Guidelines
- **Width**: 12 columns (full width is standard for filter bars)
- **Height**: 1 row
- **Common pattern**: Immediately below the dashboard title header (row 1), above the KPI row (row 2)
