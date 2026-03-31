# Component: Map (Geographic)

## ASCII Patterns

### Filled Map (Choropleth)
```
╭──────────────────────────────────────────╮
│ Revenue by State                         │
│                                          │
│       ╭──╮╭──╮                           │
│    ╭──┤WA├┤MT│╭──╮                       │
│    │OR├──┤├──┤│ND│╭─╮                    │
│    ├──┤ID├┤WY├┼──┤MN│  ╭─╮              │
│    │  ├──┤├──┤│SD├──┤  │█│ NY           │
│    │NV│UT├┤CO├┼──┤IA│──├─┤              │
│    ├──┼──┤├──┤│NE├──┤  │ │              │
│    │CA│  ├┤  ├┼──┤  │──┤ │              │
│    │██│AZ├┤NM├┤KS│MO│──┤ │              │
│    ├──┼──┤├──┤├──┼──┤  ╰─╯              │
│    ╰──╯  ╰╯  ╰╯  ╰──╯                   │
│                                          │
│  ░░ <$1M  ▓▓ $1-5M  ██ >$5M            │
╰──────────────────────────────────────────╯
```

### Symbol Map (Bubble Markers)
```
╭──────────────────────────────────────────╮
│ Office Locations — Headcount             │
│                                          │
│                    ·                      │
│            ·    ╭─╮                       │
│         ·  ╭╮  │●│  ·                    │
│       ╭──╮ ╰╯  ╰─╯                       │
│       │◉ │        ╭╮                      │
│       ╰──╯   ·    ╰╯                     │
│          ╭╮                               │
│          │●│    ·                          │
│          ╰╯                               │
│                                          │
│  · <50  ● 50-200  ◉ 200-500  ◎ 500+    │
╰──────────────────────────────────────────╯
```

### Region Map with Data Labels
```
╭──────────────────────────────────────────╮
│ Sales by Region                          │
│                                          │
│     ╭──────────────────╮                 │
│     │    NORTH          │                │
│     │    $4.2M          │                │
│     ├────────┬──────────┤                │
│     │  WEST  │  EAST    │                │
│     │  $3.1M │  $5.8M   │                │
│     ├────────┴──────────┤                │
│     │    SOUTH          │                │
│     │    $2.7M          │                │
│     ╰──────────────────╯                 │
╰──────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "map",
  "title": "(required) string — display name",
  "geo_field": "(required) string — geographic dimension (country, state, city, etc.)",
  "value_field": "(required) string — measure for color intensity or bubble size",
  "geo_type": "(optional) string — country | state | zip | city | region, default: state",
  "map_style": "(optional) string — filled | symbol, default: filled",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2-3"
  }
}
```

## Sizing Guidelines
- **Width**: 6-8 columns (maps need horizontal space for geographic context)
- **Height**: 2-3 rows (vertical space for map proportions)
- **Common pattern**: Full-width (12) for primary geographic view, or 8 columns with a 4-column side panel for filters/legend
