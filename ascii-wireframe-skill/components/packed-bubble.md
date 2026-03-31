# Component: Packed Bubble Chart

## ASCII Patterns

### Basic Packed Bubble
```
╭──────────────────────────────────────╮
│ Revenue by Product Category          │
│                                      │
│          ┌─────────┐                 │
│        ╭───╮       │                 │
│   ╭──╮ │   │╭─────╮│  ╭──╮         │
│   │  │ │Sof│││Hard ││  │  │         │
│   │SV│ │tw │││ware ││  │CS│         │
│   │C │ │are│││$42M ││  │$6│         │
│   │$8│ │$28││╰─────╯│  ╰──╯         │
│   ╰──╯ │ M ││      │               │
│         ╰───╯└─────┘                │
│      ╭──╮  ╭─╮                       │
│      │NW│  │T│                       │
│      │$5│  │3│                       │
│      ╰──╯  ╰─╯                       │
╰──────────────────────────────────────╯
```

### Simple Packed Bubble (Fewer Items)
```
╭──────────────────────────────────────╮
│ Support Tickets by Priority          │
│                                      │
│        ╭─────────╮                   │
│        │  Medium │  ╭──────╮        │
│        │   347   │  │ High │        │
│        │         │  │  218 │        │
│        ╰─────────╯  ╰──────╯        │
│    ╭───────────────╮  ╭───╮         │
│    │     Low       │  │Crt│         │
│    │     512       │  │ 43│         │
│    ╰───────────────╯  ╰───╯         │
╰──────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "packed_bubble",
  "title": "(required) string — display name",
  "category_field": "(required) string — dimension for bubble labels",
  "value_field": "(required) string — measure controlling bubble size",
  "color_field": "(optional) string — dimension or measure for bubble color",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 4-6",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 4-6 columns (bubbles need roughly square space)
- **Height**: 2 rows
- **Common pattern**: Beside a table or bar chart (6+6) for complementary detail, or standalone at 6 columns
