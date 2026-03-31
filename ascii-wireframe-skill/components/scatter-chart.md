# Component: Scatter Chart

## ASCII Patterns

### Scatter Plot
```
╭──────────────────────────────────────╮
│ Price vs Rating                       │
│                                       │
│  5.0 ┤        ·           ·          │
│  4.0 ┤     ·    ·    ·       ·       │
│  3.0 ┤  ·    ·     ·    ·           │
│  2.0 ┤     ·   ·       ·    ·       │
│  1.0 ┤  ·        ·                   │
│   0  ┼──┬──┬──┬──┬──┬──┬──┬──┬──    │
│       0  20  40  60  80  100  120    │
│                Price ($)              │
╰──────────────────────────────────────╯
```

### Scatter Plot with Color
```
╭──────────────────────────────────────╮
│ Revenue vs Satisfaction by Region     │
│                                       │
│  5.0 ┤        ◆           ●          │
│  4.0 ┤     ●    ◆    ■       ●       │
│  3.0 ┤  ◆    ■     ●    ◆           │
│  2.0 ┤     ●   ◆       ■    ●       │
│  1.0 ┤  ■        ●                   │
│   0  ┼──┬──┬──┬──┬──┬──┬──┬──┬──    │
│       0  20  40  60  80 100 120      │
│  ● North  ◆ South  ■ West           │
╰──────────────────────────────────────╯
```

### Bubble Chart
```
╭──────────────────────────────────────╮
│ Market Opportunity                    │
│                                       │
│  High ┤            ●                 │
│       ┤     ◉          ·             │
│  Med  ┤  ·      ◉         ●         │
│       ┤     ●       ·       ◉       │
│  Low  ┤  ·     ·        ●           │
│    0  ┼──┬──┬──┬──┬──┬──┬──┬──      │
│        0   200  400  600  800        │
│              Market Size              │
│  ● Large  ◉ Medium  · Small         │
╰──────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "scatter",
  "title": "(required) string — display name",
  "x_field": "(required) string — measure field for x-axis",
  "y_field": "(required) string — measure field for y-axis",
  "size_field": "(optional) string — measure field for bubble size",
  "color_field": "(optional) string — dimension field for color encoding",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 5-6",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 5-6 columns (use 6 for standalone, 5 for side-by-side)
- **Height**: 2 rows
- **Common pattern**: Paired with a table or bar chart (6+6), or standalone at full width (12) for detailed analysis
- **Best practice**: Use `color_field` to add a categorical dimension; use `size_field` for a third quantitative dimension (bubble chart)
