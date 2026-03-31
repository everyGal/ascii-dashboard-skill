# Component: Bump Chart

## ASCII Patterns

### Basic Bump Chart
```
╭──────────────────────────────────────────────────────────╮
│  Product Rankings Over Time                               │
│                                                           │
│  Rank   Q1       Q2       Q3       Q4                    │
│                                                           │
│   1     Alpha────Alpha────·───────Alpha                  │
│                           ╲      ╱                       │
│   2     Beta─────·────────Beta──╱·───Beta                │
│                  ╲       ╱      ╲                        │
│   3     Gamma────Gamma──╱────────╲──Gamma                │
│                        ╱                                  │
│   4     Delta──────────Delta────Delta────Delta            │
│                                                           │
│   5     Echo─────Echo──────Echo──────Echo                 │
│                                                           │
╰──────────────────────────────────────────────────────────╯
```

### Compact Bump Chart
```
╭──────────────────────────────────────────────────────────╮
│  Regional Sales Ranking                                   │
│                                                           │
│         Jan    Feb    Mar    Apr    May    Jun             │
│   #1     NA─────NA─────NA╲                                │
│                           ╲──EU────EU────EU              │
│   #2     EU─────EU────╱EU╱                                │
│                      ╱  ╱───NA────NA────NA               │
│   #3    APAC──APAC──╱APAC──APAC──APAC──APAC             │
│                                                           │
│   #4     LA─────LA─────LA────LA────LA────LA              │
│                                                           │
╰──────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "bump_chart",
  "title": "(required) string — display name",
  "category_field": "(required) string — dimension being ranked (e.g., product, region)",
  "time_field": "(required) string — temporal dimension for x-axis",
  "value_field": "(required) string — measure used to compute rankings",
  "max_rank": "(optional) int — limit visible ranks (default: show all)",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2"
  }
}
```

## Sizing Guidelines
- **Width**: 6-8 columns (needs horizontal space for time periods)
- **Height**: 2 rows
- **Best for**: Competitive ranking changes, leaderboard trends, position tracking over time
