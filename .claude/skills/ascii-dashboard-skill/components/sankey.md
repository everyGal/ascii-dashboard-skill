# Component: Sankey Diagram

## ASCII Patterns

### Basic Flow Diagram
```
╭──────────────────────────────────────────────────────────╮
│  Revenue Flow by Channel                                  │
│                                                           │
│  Source            Flow              Target                │
│                                                           │
│  Organic  ═══════════╲                                    │
│           ═══════════─╲══════════  Converted ($84K)       │
│  Paid     ═══════╲────╱══════════                         │
│           ═══════─╲══╱                                    │
│  Referral ════╲───═╲╱═══════════  Churned ($32K)         │
│           ════─╲═══╱                                      │
│  Direct   ══╲──═══╱════════════   Pending ($18K)         │
│           ══─╲═══╱                                        │
│                                                           │
╰──────────────────────────────────────────────────────────╯
```

### Multi-Stage Sankey
```
╭──────────────────────────────────────────────────────────╮
│  Customer Journey Flow                                    │
│                                                           │
│  Stage 1          Stage 2          Stage 3                │
│                                                           │
│  Website ════╲                                            │
│              ═╲═══ Trial ════╲                            │
│  Mobile  ════╱               ═╲═══ Paid ($120K)          │
│              ═══╲            ═╱                           │
│  Email   ═══╱   ═╲═══ Demo ═╱═══                         │
│             ════╱           ═════  Free ($45K)            │
│  Social  ══╱                                              │
│                                                           │
╰──────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "sankey",
  "title": "(required) string — display name",
  "source_field": "(required) string — dimension for source nodes",
  "target_field": "(required) string — dimension for target nodes",
  "value_field": "(required) string — measure for flow weight/thickness",
  "stages": "(optional) int — number of flow stages (default: 2)",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-8",
    "height": "(required) int — typically 2-3"
  }
}
```

## Sizing Guidelines
- **Width**: 6-8 columns (flows need horizontal space for readability)
- **Height**: 2-3 rows
- **Best for**: Flow analysis, budget allocation, customer journey mapping
- **Complexity note**: High implementation complexity — requires data densification and polygon-based rendering
