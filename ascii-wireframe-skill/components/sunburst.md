# Component: Sunburst Chart

## ASCII Patterns

### Basic Sunburst
```
╭──────────────────────────────────────────────────────────╮
│  Revenue Breakdown                                        │
│                                                           │
│                  ┌─────────┐                              │
│              ┌───┤ Online  ├───┐                          │
│          ┌───┤   └────┬────┘   ├───┐                     │
│      ┌───┤   │  ┌─────┴─────┐  │   ├───┐                │
│      │   │ NA│  │ Retail    │  │EU │   │                 │
│      │   ├───┤  └─────┬─────┘  ├───┤   │                │
│      │   │   │  ┌─────┴─────┐  │   │   │                │
│      └───┤   │  │ Wholesale │  │   ├───┘                │
│          └───┤  └───────────┘  ├───┘                     │
│              └───┤  APAC   ├───┘                          │
│                  └─────────┘                              │
│                                                           │
│  Inner ring: Region   Outer ring: Channel                │
╰──────────────────────────────────────────────────────────╯
```

### Simplified Concentric View
```
╭──────────────────────────────────────────────────────────╮
│  Spend by Department > Category                           │
│                                                           │
│           ╭───────────────────────╮                       │
│         ╭─┤ Salaries    Benefits  ├─╮                    │
│       ╭─┤ ├───────────┬───────────┤ ├─╮                  │
│       │ │ │    HR      │  Ops     │ │ │                  │
│       │ ├─┤ Training   │ Supplies ├─┤ │                  │
│       ╰─┤ │ Recruiting │ Maint.  │ ├─╯                  │
│         ╰─┤ Software   │ Hosting ├─╯                    │
│           ╰──── IT ────┴─────────╯                       │
│                                                           │
│  ● Inner: Department   ● Outer: Category                 │
╰──────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "sunburst",
  "title": "(required) string — display name",
  "hierarchy": "(required) array of strings — dimension fields from innermost to outermost ring",
  "value_field": "(required) string — measure for segment sizing",
  "show_labels": "(optional) bool — show segment labels, default: true",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 5-6",
    "height": "(required) int — typically 2-3"
  }
}
```

## Sizing Guidelines
- **Width**: 5-6 columns (square aspect ratio preferred)
- **Height**: 2-3 rows
- **Best for**: Hierarchical breakdowns, part-to-whole at multiple levels, organizational spend analysis
- **Alternative**: Consider nested treemaps or drill-down pie charts for similar insights with lower complexity
