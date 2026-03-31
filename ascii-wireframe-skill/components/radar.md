# Component: Radar / Spider Chart

## ASCII Patterns

### Basic Radar Chart
```
╭──────────────────────────────────────────────────────────╮
│  Team Performance Radar                                   │
│                                                           │
│              Quality                                      │
│                 ╱╲                                        │
│                ╱  ╲                                       │
│        Speed  ╱ ·· ╲  Accuracy                           │
│              ╱·    ·╲                                     │
│         ────·────────·────                                │
│              ╲·    ·╱                                     │
│   Teamwork   ╲ ·· ╱  Innovation                          │
│                ╲  ╱                                       │
│                 ╲╱                                        │
│            Reliability                                    │
│                                                           │
│  ── Boundary   ·· Data                                   │
╰──────────────────────────────────────────────────────────╯
```

### Multi-Series Radar
```
╭──────────────────────────────────────────────────────────╮
│  Product Comparison                                       │
│                                                           │
│               Design                                      │
│                 ╱╲                                        │
│               ╱░░╲                                       │
│     Price    ╱░▓▓░╲   Features                           │
│             ╱░▓  ▓░╲                                     │
│        ────░▓────▓░────                                  │
│             ╲░▓  ▓░╱                                     │
│   Support    ╲░▓▓░╱   Performance                        │
│               ╲░░╱                                       │
│                ╲╱                                        │
│             Usability                                    │
│                                                           │
│  ░░ Product A   ▓▓ Product B                             │
╰──────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "radar",
  "title": "(required) string — display name",
  "axes": "(required) array of strings — field names for each axis (minimum 3)",
  "category_field": "(required) string — dimension to compare (e.g., product, team)",
  "normalize": "(optional) bool — normalize all axes to 0-1 scale, default: true",
  "show_grid": "(optional) bool — show concentric grid rings, default: true",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 4-6",
    "height": "(required) int — typically 2-3"
  }
}
```

## Sizing Guidelines
- **Width**: 4-6 columns (square aspect ratio works best)
- **Height**: 2-3 rows
- **Best for**: Multi-dimensional comparisons, performance profiles, competitive analysis
- **Complexity note**: High implementation complexity — requires trigonometric coordinate transformations
