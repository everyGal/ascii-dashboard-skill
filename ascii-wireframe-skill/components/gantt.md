# Component: Gantt Chart

## ASCII Patterns

### Basic Gantt
```
╭──────────────────────────────────────────────────────────╮
│  Project Timeline                                        │
│                                                          │
│  Task              Jan    Feb    Mar    Apr    May       │
│  ──────────────────────────────────────────────────      │
│  Platform v2       ███████████████                       │
│  API Rebuild              ████████████████               │
│  Data Migration                 ████████████             │
│  Security Audit                       ███████            │
│  Mobile App        ██████████████████████████████        │
│  Infra Upgrade            ████████████                   │
│                                                          │
│  ███ On Track  ░░░ At Risk  ▓▓▓ Complete                 │
╰──────────────────────────────────────────────────────────╯
```

### Gantt with Milestones
```
╭──────────────────────────────────────────────────────────╮
│  Q2 Roadmap                                              │
│                                                          │
│  Phase         Apr        May        Jun                 │
│  ──────────────────────────────────────────              │
│  Discovery     ████████◆                                 │
│  Design               ████████◆                         │
│  Build                        ████████████◆             │
│  Testing              ░░░░░░░░░░░░░░░                   │
│  Launch                                   ◆             │
│                                                          │
│  ◆ Milestone  ░░░ Parallel track                        │
╰──────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "gantt",
  "title": "(required) string — display name",
  "category_field": "(required) string — task or project dimension",
  "start_field": "(required) string — start date field",
  "end_field": "(required) string — end date field",
  "color_field": "(optional) string — dimension for bar color (e.g. Status)",
  "milestone_field": "(optional) string — boolean field marking milestone tasks",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 7-12",
    "height": "(required) int — typically 2-3"
  }
}
```

## Sizing Guidelines
- **Width**: 7-12 columns (timeline needs horizontal space for date axis)
- **Height**: 2-3 rows (more rows for more tasks)
- **Best for**: Project timelines, sprint planning, roadmap visualization
