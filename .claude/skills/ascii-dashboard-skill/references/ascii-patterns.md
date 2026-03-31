# ASCII Patterns Reference

## Box-Drawing Character Set

### Dashboard Frame
```
╔  ═  ╗    top border
║       ║    sides
╠  ═  ╣    section divider
╚  ═  ╝    bottom border
```

### Widget Border (rounded)
```
╭  ─  ╮    top
│       │    sides
╰  ─  ╯    bottom
```

### Inner Table Grid
```
┌  ─  ┬  ─  ┐    top
│       │       │    row
├  ─  ┼  ─  ┤    divider
└  ─  ┴  ─  ┘    bottom
```

### Axis Characters
```
┤    y-axis tick mark
┼    axis origin (intersection)
┬    x-axis tick mark (pointing up into chart)
```

---

## Full Dashboard Frame Template

```
╔══════════════════════════════════════════════════════════════╗
║  Dashboard Title                         [Filter A ▾]        ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  (widget rows go here)                                       ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

- Filters appear in the header row, right-aligned, separated by spaces.
- Use `[Label ▾]` for dropdown filters.
- Section dividers (`╠═╣`) may be added between major logical groups if helpful.

---

## Widget Border Template

```
╭──────────────────────────────────────╮
│ Widget Title                          │
│                                       │
│  (content)                            │
│                                       │
╰──────────────────────────────────────╯
```

---

## Chart-Specific ASCII Patterns

### Bar Chart — Vertical
```
│  120 ┤
│  100 ┤  ██
│   80 ┤  ██  ██
│   60 ┤  ██  ██  ██
│   40 ┤  ██  ██  ██  ██
│   20 ┤  ██  ██  ██  ██  ██
│    0 ┼──┴───┴───┴───┴───┴──
│       NA   EU  APAC  LA  MEA
```

### Bar Chart — Horizontal
```
│  Product A  ████████████████  $142K
│  Product B  ████████████      $108K
│  Product C  █████████         $87K
│  Product D  ██████            $62K
```

### Bar Chart — Stacked (two series: `██` and `▓▓`)
```
│  100 ┤  ▓▓
│   80 ┤  ██  ▓▓
│   60 ┤  ██  ██  ▓▓
│   40 ┤  ██  ██  ██
│    0 ┼──┴───┴───┴──
│       Q1   Q2   Q3
│       ██ Series A  ▓▓ Series B
```

### Line Chart — Single
```
│  100 ┤              ╱──╲
│   80 ┤         ╱──╱     ╲──╱╲
│   60 ┤    ╱──╱                ╲
│   40 ┤  ╱                      ╲
│   20 ┤╱
│    0 ┼──┬──┬──┬──┬──┬──┬──┬──┬──
│       J  F  M  A  M  J  J  A  S
```

### Line Chart — Multi-Series (`──` solid, `╌╌` dashed)
```
│   ── Series A
│   ╌╌ Series B
│
│  80 ┤         ╱──╱
│  60 ┤    ╱──╱      ╌╌╌╌╌╌╌╌
│  40 ┤  ╱      ╌╌╌╌╌
│  20 ┤╱   ╌╌╌╌
│   0 ┼──┬──┬──┬──┬──┬──
```

### Area Chart
```
│  100 ┤              ╱──╲
│   80 ┤         ╱──╱▓▓▓▓▓╲──╱╲
│   60 ┤    ╱──╱▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓╲
│   40 ┤  ╱▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓╲
│   20 ┤╱▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓
│    0 ┼──┬──┬──┬──┬──┬──┬──┬──┬──
```

### Pie / Donut Chart
```
╭──────────────────────────────────────╮
│ Revenue by Channel                    │
│                                       │
│        ╭──────╮                       │
│      ╱           ╲   ██ Online  42%   │
│     │   ██  ▓▓   │   ▓▓ Retail  33%   │
│     │   ▒▒  ░░   │   ▒▒ Partner 15%   │
│      ╲           ╱   ░░ Other   10%   │
│        ╰──────╯                       │
╰──────────────────────────────────────╯
```
Donut: add concentric inner ring `○` or leave center blank with label.

### KPI Card
```
╭───────────╮
│ Revenue    │
│ $1.2M      │
│ ▲ 12.5%    │
╰───────────╯
```
Delta indicators: `▲` positive, `▼` negative, `─` neutral.

### Table (text)
```
│  Account     │ Revenue  │ Growth  │
│  ────────────┼──────────┼─────────│
│  Acme Corp   │  $820K   │ ▲ 12%   │
│  GlobalTech  │  $645K   │ ▲  8%   │
│  Pinnacle    │  $410K   │ ▼  3%   │
```

### Table (highlight / heatmap cells)
```
│  Account     │ Revenue  │ Margin  │
│  ────────────┼──────────┼─────────│
│  Acme Corp   │ ██ $820K │ ██  42% │
│  GlobalTech  │ ██ $645K │ █   38% │
│  Pinnacle    │ █  $410K │ ░   28% │
```
Intensity scale: `██` high · `█` medium · `░` low.

### Funnel
```
│  ████████████████████  Visitors   10,000
│    ████████████████    Leads       6,200
│      ████████████      MQLs        3,100
│        ████████        SQLs        1,450
│          ████          Closed        380
```

### Waterfall
```
│  500 ┤  ██
│  400 ┤  ██  ░░
│  300 ┤  ██  ░░  ██
│  200 ┤  ██  ░░  ██  ░░
│  100 ┤  ██  ░░  ██  ░░  ██
│    0 ┼──┴───┴───┴───┴───┴──
│       Base  +A  -B   +C  Net
```
`██` increase · `░░` decrease.

### Treemap
```
┌──────────────┬────────┐
│              │ Mid-   │
│  Enterprise  │ Market │
│   $2.1M      │ $1.1M  │
│   50.0%      │ 26.2%  │
├──────────────┼───┬────┤
│   SMB        │Gov│    │
│   $0.7M      │$0.│    │
└──────────────┴───┴────┘
```

### Heatmap (matrix)
```
│         │ Jan  │ Feb  │ Mar  │ Apr  │
│  ────────┼──────┼──────┼──────┼──────│
│  North   │  ██  │  ██  │  ▓▓  │  ░░  │
│  South   │  ▓▓  │  ██  │  ██  │  ██  │
│  East    │  ░░  │  ▓▓  │  ██  │  ▓▓  │
│  West    │  ██  │  ░░  │  ▓▓  │  ██  │
```
`██` high · `▓▓` medium-high · `▒▒` medium · `░░` low.

### Scatter / Bubble
```
│  100 ┤               ●
│   80 ┤          ○         ●
│   60 ┤     ◯                   ●
│   40 ┤  ○         ◯
│   20 ┤       ●
│    0 ┼──┬──┬──┬──┬──┬──┬──┬──
│         0   20  40  60  80  100
```
Bubble size: `●` large · `○` medium · `·` small.

### Gauge / Speedometer
```
╭──────────────────────────╮
│ Customer Satisfaction     │
│                           │
│     ╭──────────╮          │
│    ╱  ████░░░░  ╲         │
│   │   ████░░░░   │  72%   │
│   │      ↑       │        │
│    ╲─────────────╱        │
│      Low   Mid  High      │
╰──────────────────────────╯
```

### Sparkline (inline mini chart)
```
│ Revenue   ╱╲╱──╱   $1.2M  ▲ 8%  │
│ Users     ╱───╱╲   45.2K  ▲ 3%  │
│ Churn      ╲╱╲╱    2.1%   ▼ 0.2% │
```

### Bullet Chart
```
│  Revenue  ░░░░░░████████│   $1.2M / $1.5M target  │
│  Margin   ░░░████████   │   38% / 40% target       │
│  NPS      ░░░░░░░█████  │   52 / 60 target         │
```
Background `░░░░░░` = range, fill `████` = actual, `│` = target marker.

### Gantt
```
│  Task              │ Jan  │ Feb  │ Mar  │ Apr  │ May  │
│  ──────────────────┼──────┼──────┼──────┼──────┼──────│
│  Discovery         │ ████ │      │      │      │      │
│  Design            │ ████ │ ████ │      │      │      │
│  Development       │      │ ████ │ ████ │ ████ │      │
│  QA                │      │      │      │ ████ │ ████ │
```

### Calendar Heatmap
```
│     Mon  Tue  Wed  Thu  Fri
│  W1  ░░   ██   ▓▓   ██   ░░
│  W2  ██   ▓▓   ██   ░░   ▓▓
│  W3  ▓▓   ██   ░░   ██   ██
│  W4  ██   ░░   ██   ▓▓   ██
```

### Filter Bar
```
╭──────────────────────────────────────────────────────────╮
│  [Region ▾ All]  [Product ▾ All]  [Date Range ▾ YTD]     │
╰──────────────────────────────────────────────────────────╯
```

### Text Header
```
╭──────────────────────────────────────╮
│  ▌ Section Title                      │
│  Subtitle or description line here    │
╰──────────────────────────────────────╯
```

---

## Sizing Quick Reference

| Component       | Typical Width | Typical Height |
|-----------------|---------------|----------------|
| KPI Card        | 2–3 cols      | 1 row          |
| Bar Chart       | 4–6 cols      | 2 rows         |
| Line Chart      | 5–8 cols      | 2 rows         |
| Area Chart      | 6–8 cols      | 2 rows         |
| Pie / Donut     | 4–6 cols      | 2 rows         |
| Table           | 8–12 cols     | 2–3 rows       |
| Treemap         | 4–6 cols      | 2 rows         |
| Heatmap         | 6–8 cols      | 2 rows         |
| Funnel          | 4–6 cols      | 2–3 rows       |
| Waterfall       | 6–8 cols      | 2 rows         |
| Scatter         | 4–6 cols      | 2 rows         |
| Gauge           | 3–4 cols      | 2 rows         |
| Sparkline       | 4–6 cols      | 1 row          |
| Bullet Chart    | 6–8 cols      | 1–2 rows       |
| Gantt           | 8–12 cols     | 2–3 rows       |
| Filter Bar      | 12 cols       | 1 row          |
| Text Header     | 4–12 cols     | 1 row          |

---

## Common Layout Patterns

### KPI Row (4 cards)
```
col:  1───3  4───6  7───9  10──12
       KPI    KPI    KPI    KPI
```

### KPI Row (6 cards)
```
col:  1─2  3─4  5─6  7─8  9─10  11─12
       KPI  KPI  KPI  KPI  KPI   KPI
```

### Two Charts Side-by-Side
```
col:  1────────6  7────────12
       Chart A     Chart B
```

### Featured Chart + Sidebar
```
col:  1──────────8  9────12
       Main Chart   Side
```

### Full-Width Chart
```
col:  1─────────────────────12
             Chart
```

### Mixed Row: Gauge + Sparklines
```
col:  1──3  4──────────────12
       Gauge   Sparkline stack
```
