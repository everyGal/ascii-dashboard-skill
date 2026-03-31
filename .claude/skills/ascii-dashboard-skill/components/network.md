# Component: Network / Graph

## ASCII Patterns

### Basic Network Graph
```
╭──────────────────────────────────────────────────────────╮
│  Service Dependencies                                     │
│                                                           │
│         ╭───────╮                                         │
│         │  API  │                                         │
│         ╰───┬───╯                                         │
│         ╱   │   ╲                                         │
│    ╭───╮    │    ╭───╮                                    │
│    │ DB│    │    │Cache│                                  │
│    ╰───╯    │    ╰───╯                                    │
│             │                                             │
│         ╭───╴───╮                                         │
│         │ Queue │                                         │
│         ╰───────╯                                         │
│                                                           │
│  ●── Service  ──── Dependency                            │
╰──────────────────────────────────────────────────────────╯
```

### Social/Org Network
```
╭──────────────────────────────────────────────────────────╮
│  Team Collaboration Network                               │
│                                                           │
│    Alice ─────── Bob                                      │
│      │     ╲   ╱  │                                      │
│      │      Carol  │                                      │
│      │     ╱   ╲  │                                      │
│    Dave ─────── Eve                                       │
│      │                                                    │
│    Frank                                                  │
│                                                           │
│  ● Node size = connections                               │
│  ── Line thickness = interaction frequency               │
╰──────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "network",
  "title": "(required) string — display name",
  "node_field": "(required) string — dimension for nodes",
  "edge_source_field": "(required) string — source node for each edge",
  "edge_target_field": "(required) string — target node for each edge",
  "node_size_field": "(optional) string — measure controlling node size",
  "edge_weight_field": "(optional) string — measure controlling edge thickness",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2-3"
  }
}
```

## Sizing Guidelines
- **Width**: 6-8 columns (roughly square aspect ratio)
- **Height**: 2-3 rows
- **Best for**: Dependency graphs, org charts, collaboration networks, flow analysis
- **Complexity note**: High complexity — requires pre-computed node positions; force-directed layout cannot be computed in most charting tools without a dedicated library
