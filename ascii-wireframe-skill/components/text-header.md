# Component: Text Header

## ASCII Patterns

### Dashboard Title Header
```
╔══════════════════════════════════════════════════════════════╗
║  Sales Performance Dashboard                  Q4 2025       ║
╚══════════════════════════════════════════════════════════════╝
```

### Section Header
```
╭──────────────────────────────────────────────────────────────╮
│  ▌ Pipeline Overview                                         │
╰──────────────────────────────────────────────────────────────╯
```

### Divider with Label
```
─────────────────────────── Revenue ─────────────────────────────
```

### Rich Text Header with Subtitle
```
╭──────────────────────────────────────────────────────────────╮
│  Executive Summary                                           │
│  Fiscal Year 2025 · All Regions · Updated: Jan 1, 2026      │
╰──────────────────────────────────────────────────────────────╯
```

### Annotation Block
```
╭──────────────────────────────────────────────────────────────╮
│  ⚠ Note: Data reflects current quarter only.                 │
│  Historical comparison uses prior year same period.          │
╰──────────────────────────────────────────────────────────────╯
```

## Spec Template
```json
{
  "id": "(required) string — unique snake_case identifier",
  "type": "text_header",
  "title": "(required) string — primary text content",
  "subtitle": "(optional) string — secondary text below the title",
  "align": "(optional) left | center | right — default: left",
  "style": "(optional) h1 | h2 | annotation | divider — default: h1",
  "grid": {
    "col": "(required) int 1-12",
    "row": "(required) int",
    "width": "(required) int — typically 6-12",
    "height": "(required) int — typically 1"
  }
}
```

## Sizing Guidelines
- **Width**: 6-12 columns (full width for dashboard title, narrower for section headers)
- **Height**: 1 row
- **Common pattern**: Row 1 as full-width dashboard title, or between content sections as dividers
