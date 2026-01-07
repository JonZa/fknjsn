# CLAUDE.md

This file provides guidance to Claude Code when working with this repository.

## Project Overview

A JSON comparison tool built with Vue 3. Paste JSON into rows, compare side-by-side in columns, search within each block. Dark mode IDE-like interface.

## Development Commands

**Local Development Server:**
```bash
python3 -m http.server 8000
```
Access at http://localhost:8000/app/

## Architecture

**Single File + CDN Dependencies:**
- `app/index.html` - Vue 3 SFC-style app with inline CSS/JS
- Vue 3.4.21 and vue-json-pretty 2.4.0 loaded from unpkg CDN
- No build step required

**Core Components:**
1. **Row/Column System** - Rows contain up to 4 JSON blocks for comparison
2. **JSON Rendering** - vue-json-pretty with full expansion and syntax highlighting
3. **Search/Filter** - Per-block search with memoized filtering (filteredData)
4. **Dark Theme** - VS Code Dark+ inspired CSS custom properties
5. **Persistence** - localStorage saves rows, selection, counters

**Data Flow:**
- Paste JSON → parse → add to selected row's blocks
- Block search → filterJSON() → filteredData (debounced 150ms)
- All state → localStorage (debounced 500ms, excludes filteredData)

**Key Functions:**
- `selectRow(id)` - Set active row for paste target
- `addColumn(rowId)` - Add empty column to row
- `addRow()` - Add new row, auto-scroll
- `removeRow(rowId)` / `removeColumn(rowId, blockId)` - Remove with cleanup
- `filterJSON(data, search)` - Recursive JSON filtering

**LocalStorage Schema:**
```javascript
{
  rows: [{ id, blocks: [{ id, data, search }] }],
  selectedRowId: number,
  blockIdCounter: number,
  rowIdCounter: number
}
```

## UI Behavior

- Minimum 4 rows always visible
- Auto-add row when all rows have data
- Max 4 columns per row
- Click row to select (blue highlight)
- Paste goes to selected row's first empty column or creates new column
