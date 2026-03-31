# ASCII Wireframe Patterns Reference

A reference guide for building ASCII wireframes using box-drawing characters, block elements, and layout conventions.

---

## Box-Drawing Characters

### Single-Line Borders
```
┌─────────────────┐
│                 │
│   content area  │
│                 │
└─────────────────┘
```

| Character | Unicode | Use |
|-----------|---------|-----|
| `┌` | U+250C | Top-left corner |
| `┐` | U+2510 | Top-right corner |
| `└` | U+2514 | Bottom-left corner |
| `┘` | U+2518 | Bottom-right corner |
| `─` | U+2500 | Horizontal line |
| `│` | U+2502 | Vertical line |
| `├` | U+251C | Left T-junction |
| `┤` | U+2524 | Right T-junction |
| `┬` | U+252C | Top T-junction |
| `┴` | U+2534 | Bottom T-junction |
| `┼` | U+253C | Cross junction |

### Double-Line Borders
```
╔═════════════════╗
║                 ║
║   content area  ║
║                 ║
╚═════════════════╝
```

| Character | Unicode | Use |
|-----------|---------|-----|
| `╔` | U+2554 | Top-left corner |
| `╗` | U+2557 | Top-right corner |
| `╚` | U+255A | Bottom-left corner |
| `╝` | U+255D | Bottom-right corner |
| `═` | U+2550 | Horizontal double |
| `║` | U+2551 | Vertical double |
| `╠` | U+2560 | Left T-junction |
| `╣` | U+2563 | Right T-junction |
| `╦` | U+2566 | Top T-junction |
| `╩` | U+2569 | Bottom T-junction |
| `╬` | U+256C | Cross junction |

### Mixed Single/Double
```
╒═══════╤═══════╕
│       │       │
╞═══════╪═══════╡
│       │       │
╘═══════╧═══════╛
```

---

## Block Fill Characters

Used for bar charts, progress indicators, and density fills.

| Character | Unicode | Fill Level | Use |
|-----------|---------|-----------|-----|
| `█` | U+2588 | 100% | Full block — max value bars |
| `▓` | U+2593 | 75% | Dark shade |
| `▒` | U+2592 | 50% | Medium shade |
| `░` | U+2591 | 25% | Light shade |
| `▄` | U+2584 | Bottom half | Lower half block |
| `▀` | U+2580 | Top half | Upper half block |
| `▌` | U+258C | Left half | Left half block |
| `▐` | U+2590 | Right half | Right half block |

### Fractional Blocks (for smooth bars)
| Character | Unicode | Width |
|-----------|---------|-------|
| `▏` | U+258F | 1/8 |
| `▎` | U+258E | 2/8 |
| `▍` | U+258D | 3/8 |
| `▌` | U+258C | 4/8 |
| `▋` | U+258B | 5/8 |
| `▊` | U+258A | 6/8 |
| `▉` | U+2589 | 7/8 |
| `█` | U+2588 | 8/8 |

---

## Layout Sizing Conventions

### 12-Column Grid

All dashboards use a 12-column grid. Each column = 6 characters wide (plus 1 for gutter) in wireframes.

```
col: 1   2   3   4   5   6   7   8   9   10  11  12
     |    |    |    |    |    |    |    |    |    |    |    |
     ┌────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬────┐
```

| col_span | Approx chars wide | Label |
|----------|-------------------|-------|
| 2        | ~12               | Narrow |
| 3        | ~18               | Quarter |
| 4        | ~24               | Third |
| 6        | ~36               | Half |
| 8        | ~48               | Two-thirds |
| 9        | ~54               | Three-quarters |
| 12       | ~72               | Full |

### Row Heights

| row_height | Approx lines tall | Use |
|------------|-------------------|-----|
| 1          | 3–4 lines         | KPI card, text header |
| 2          | 6–8 lines         | Sparkline, filter bar |
| 3          | 10–12 lines       | Small chart |
| 4          | 14–16 lines       | Standard chart |
| 5          | 18–20 lines       | Large chart, table |
| 6          | 22–24 lines       | Full-height chart |

---

## Chart Pattern Library

### KPI Card
```
┌──────────────────────────┐
│  Metric Title            │
│                          │
│        42,891            │
│    ▲ +12.3% vs prev      │
└──────────────────────────┘
```

### Horizontal Bar Chart
```
┌─────────────────────────────────┐
│ Category A  ████████████░░  78% │
│ Category B  █████████░░░░░  61% │
│ Category C  ███████░░░░░░░  48% │
│ Category D  █████░░░░░░░░░  34% │
│ Category E  ███░░░░░░░░░░░  22% │
└─────────────────────────────────┘
```

### Vertical Bar Chart
```
┌──────────────────────────────┐
│  100│        ██             │
│   80│     ██ ██ ██          │
│   60│  ██ ██ ██ ██          │
│   40│  ██ ██ ██ ██ ██       │
│   20│  ██ ██ ██ ██ ██ ██    │
│    0└──────────────────────  │
│      Jan Feb Mar Apr May Jun │
└──────────────────────────────┘
```

### Line Chart
```
┌──────────────────────────────┐
│  100│              ╭──╮      │
│   80│         ╭───╯  ╰─╮    │
│   60│    ╭───╯          ╰╮  │
│   40│╭──╯                ╰  │
│   20│                       │
│    0└──────────────────────  │
│      Jan Feb Mar Apr May Jun │
└──────────────────────────────┘
```

### Area Chart
```
┌──────────────────────────────┐
│  100│              ╭──╮      │
│   80│         ╭───╯▓▓▓╰─╮   │
│   60│    ╭───╯▓▓▓▓▓▓▓▓▓▓╰╮  │
│   40│╭──╯▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓╰  │
│   20│▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓  │
│    0└──────────────────────  │
│      Jan Feb Mar Apr May Jun │
└──────────────────────────────┘
```

### Pie / Donut Chart
```
       ┌──────────────────┐
       │     ╭───╮        │
       │   ╱  A  ╲        │
       │  │  45%  │  ─ A  │
       │   ╲ ─── ╱   ─ B  │
       │  ╱╲     ╱╲  ─ C  │
       │ ╱ B╲   ╱ C╲      │
       │╱ 30%╲ ╱ 25%╲     │
       └──────────────────┘
```

### Scatter Plot
```
┌──────────────────────────────┐
│  100│  ·        ·   ·        │
│   80│     ·  ·     ·         │
│   60│  ·     ·  ·    ·       │
│   40│     ·     ·  ·         │
│   20│  ·  ·        ·         │
│    0└──────────────────────  │
│      0   20  40  60  80  100 │
└──────────────────────────────┘
```

### Table
```
┌──────────────┬───────┬───────┬───────┐
│ Name         │ Q1    │ Q2    │ Q3    │
├──────────────┼───────┼───────┼───────┤
│ Alpha        │ 1,200 │ 1,450 │ 1,380 │
│ Beta         │   890 │   920 │ 1,100 │
│ Gamma        │ 2,100 │ 1,980 │ 2,240 │
│ Delta        │   445 │   510 │   490 │
├──────────────┼───────┼───────┼───────┤
│ Total        │ 4,635 │ 4,860 │ 5,210 │
└──────────────┴───────┴───────┴───────┘
```

### Heatmap
```
┌────────────────────────────────────┐
│       Mon  Tue  Wed  Thu  Fri      │
│  9am  ░░░  ▒▒▒  ███  ▒▒▒  ░░░     │
│ 10am  ▒▒▒  ███  ███  ███  ▒▒▒     │
│ 11am  ███  ███  ▓▓▓  ███  ███     │
│  1pm  ▒▒▒  ▓▓▓  ███  ▓▓▓  ▒▒▒     │
│  2pm  ░░░  ▒▒▒  ▓▓▓  ▒▒▒  ░░░     │
│  3pm  ░░░  ░░░  ▒▒▒  ░░░  ░░░     │
└────────────────────────────────────┘
```

### Gauge / Radial
```
       ┌──────────────────┐
       │    ╭─────────╮   │
       │  ╱   ░░▓▓███   ╲ │
       │ │  ░░░░▓▓▓███  │ │
       │  ╲       ↑     ╱ │
       │    ╰─────┼───╯   │
       │          68%      │
       └──────────────────┘
```

### Funnel
```
┌──────────────────────────────┐
│  ████████████████████  100%  │
│    ██████████████████   72%  │
│      ████████████████   54%  │
│        ██████████████   38%  │
│          ████████████   21%  │
│            ██████████   12%  │
└──────────────────────────────┘
```

### Waterfall Chart
```
┌──────────────────────────────┐
│  120│     ██               │ │
│  100│  ██ ██ ▓▓            │ │
│   80│  ██ ██ ▓▓ ██         │ │
│   60│  ██    ▓▓ ██ ░░      │ │
│   40│        ▓▓    ░░ ██   │ │
│   20│              ░░ ██   │ │
│    0└─────────────────────  │ │
│     Start +A  -B  +C  -D End│ │
└──────────────────────────────┘
  ██ Increase  ▓▓ Base  ░░ Decrease
```

### Treemap
```
┌──────────────────────────────────┐
│ ┌─────────────┬────────┬───────┐ │
│ │             │        │  E    │ │
│ │      A      │   C    │ 8%    │ │
│ │    35%      │  18%   ├───────┤ │
│ │             │        │  F    │ │
│ ├─────────────┤        │ 6%    │ │
│ │      B      ├────────┴───────┤ │
│ │    22%      │       D  11%   │ │
│ └─────────────┴────────────────┘ │
└──────────────────────────────────┘
```

### Bullet Chart
```
┌──────────────────────────────────┐
│ Revenue                          │
│ ░░░░░░░░░▓▓▓▓▓▓▓▓▓▓▓▓▓██████│   │
│          ↑target      ↑actual    │
│                                  │
│ Margin                           │
│ ░░░░░░░░░░░░░▓▓▓▓▓▓▓▓▓█████│    │
│              ↑target  ↑actual    │
└──────────────────────────────────┘
```

### Gantt Chart
```
┌──────────────────────────────────────┐
│ Task         │Jan│Feb│Mar│Apr│May│Jun│
├──────────────┼───┼───┼───┼───┼───┼──┤
│ Planning     │███│   │   │   │   │  │
│ Design       │▒▒▒│███│   │   │   │  │
│ Development  │   │▒▒▒│███│███│   │  │
│ Testing      │   │   │   │▒▒▒│███│  │
│ Launch       │   │   │   │   │▒▒▒│██│
└──────────────────────────────────────┘
```

### Sparkline
```
┌──────────────────────────┐
│ Revenue  ╭─╮   ╭──╮  ▲  │
│          │ ╰─╮╯  ╰╮╯ 12%│
└──────────────────────────┘
```

### Filter Bar
```
┌─────────────────────────────────────────────┐
│ [Date Range ▼] [Region ▼] [Category ▼] [🔍] │
└─────────────────────────────────────────────┘
```

### Text / Header
```
┌──────────────────────────────────────────┐
│  Dashboard Title                         │
│  Subtitle or description text here       │
│                              Updated: now│
└──────────────────────────────────────────┘
```

---

## Multi-Row Layout Patterns

### 4 KPI Cards + Chart Below
```
┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐
│ KPI 1    │ │ KPI 2    │ │ KPI 3    │ │ KPI 4    │
│  1,234   │ │  56.7%   │ │  $89K    │ │  ▲ 4.2%  │
└──────────┘ └──────────┘ └──────────┘ └──────────┘
┌──────────────────────────┐ ┌────────────────────┐
│                          │ │                    │
│       Line Chart         │ │     Bar Chart      │
│                          │ │                    │
└──────────────────────────┘ └────────────────────┘
```

### Two-Column with Sidebar
```
┌──────────────────────────────┐ ┌──────────────┐
│                              │ │  Filter Bar  │
│       Main Chart             │ ├──────────────┤
│                              │ │   KPI Card   │
│                              │ ├──────────────┤
│                              │ │   KPI Card   │
└──────────────────────────────┘ └──────────────┘
```

### Full-Width Header + Grid
```
┌──────────────────────────────────────────────────┐
│  Executive Summary Dashboard          2024 Q4    │
└──────────────────────────────────────────────────┘
┌────────────┐ ┌────────────┐ ┌────────────┐
│   KPI 1    │ │   KPI 2    │ │   KPI 3    │
└────────────┘ └────────────┘ └────────────┘
┌──────────────────────────────────────────────────┐
│                    Main Chart                    │
└──────────────────────────────────────────────────┘
```

---

## Axis and Annotation Conventions

### Y-Axis Labels
```
│ 100 ┤
│  80 ┤
│  60 ┤
│  40 ┤
│  20 ┤
│   0 ┼───────────────────
```

### X-Axis Labels
```
      ───────────────────
      Jan  Feb  Mar  Apr
```

### Trend Indicators
| Symbol | Meaning |
|--------|---------|
| `▲` | Up / Positive trend |
| `▼` | Down / Negative trend |
| `→` | Flat / No change |
| `↑` | Strong increase |
| `↓` | Strong decrease |
| `●` | Data point |
| `✕` | Filtered out / N/A |

### Legend Patterns
```
■ Series A   □ Series B   ▩ Series C   ░ Series D
```

---

## Responsive Breakpoints

When `col_span` would cause overlap in narrow viewports, components stack vertically:

| Breakpoint | Behavior |
|------------|----------|
| Full (12 cols) | Side-by-side as specified |
| Medium (8 cols) | 3-col components become 4-col |
| Narrow (4 cols) | All components go full-width |
