# Component: Funnel

## ASCII Patterns

### Basic Sales Funnel
```
╭──────────────────────────────────────────╮
│  Sales Pipeline Funnel                   │
│                                          │
│  Sessions    ████████████████████  12,400 │
│                    92.3%                 │
│  Leads       ███████████████████   8,200  │
│                    48.8%                 │
│  MQLs        ██████████████        4,000  │
│                    45.0%                 │
│  SQLs        ██████████           1,800   │
│                    33.3%                 │
│  Won         ██████                 600   │
│                                          │
│  Overall Conversion: 4.8%                │
╰──────────────────────────────────────────╯
```

### Centered Funnel
```
╭──────────────────────────────────────────╮
│  User Onboarding Funnel                  │
│                                          │
│       ████████████████████████████       │
│            Signed Up — 50,000            │
│         ████████████████████████         │
│          Activated — 38,500 (77%)        │
│           ████████████████████           │
│         Completed — 22,100 (57%)         │
│              ██████████████              │
│          Subscribed — 8,840 (40%)        │
│                ██████████                │
│           Renewed — 5,300 (60%)          │
│                                          │
╰──────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string",
  "type": "funnel",
  "title": "(required) string",
  "stages": [
    {
      "label": "(required) string — stage name",
      "value_field": "(required) string — metric for this stage"
    }
  ],
  "show_conversion": "(optional) bool — show % between stages, default: true",
  "show_overall": "(optional) bool — show overall conversion rate, default: true",
  "centered": "(optional) bool — center-align bars, default: false",
  "grid": {
    "col": "(required) int",
    "row": "(required) int",
    "width": "(required) int — typically 4-6",
    "height": "(required) int — typically 2-3"
  }
}
```

## Sizing Guidelines
- **Width**: 4-6 columns
- **Height**: 2-3 rows
- **Best for**: Conversion pipelines, process drop-off analysis
