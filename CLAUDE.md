# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-page JSON formatter web application built as a self-contained HTML file. The app provides real-time JSON formatting, validation, and management capabilities with persistent storage.

## Development Commands

**Local Development Server:**
```bash
python3 -m http.server 8000
```
Access the application at http://localhost:8000/app/

## Architecture

**Single File Architecture:**
- `app/index.html` - Self-contained application with inline CSS and JavaScript
- No external dependencies or build process required
- All assets (favicons, icons) are relative to the app directory

**Core Components:**

1. **JSON Processing Engine** - Real-time parsing and formatting with error handling
2. **Pin Management System** - Persistent storage of formatted outputs with custom naming
3. **Icon-Based UI** - SVG icons for all actions (copy, pin, download, maximize, remove)
4. **LocalStorage Persistence** - Automatic saving/loading of pinned outputs across sessions

**Data Flow:**
- Input textarea → JSON.parse() → JSON.stringify(obj, null, 2) → Output textarea
- Pin action → localStorage → Dynamic DOM creation
- All pinned outputs auto-resize to content height

**Key Functions:**
- `formatJSON()` - Core JSON processing with error states
- `createPinnedSection()` - Dynamic creation of pinned output blocks
- `copyToClipboard()` - Handles icon restoration after "Copied!" feedback
- `downloadJSON()` - Creates downloadable .json files with custom naming

**Icon Integration:**
- All buttons use SVG icons from `app/icons/` directory
- Icons are styled with CSS filter for white coloring
- Copy button properly restores icon after temporary "Copied!" text

**LocalStorage Schema:**
```javascript
pinnedData = [
  {
    id: number,        // Sequential counter
    content: string,   // Formatted JSON
    name: string|null  // Optional custom name
  }
]
```

**Button Behavior:**
- Main output: Copy, Pin (with name prompt), Download, Maximize (toggleable)
- Pinned outputs: Copy, Download (with custom filename), Remove (auto-maximized)

## Development Notes

- Project configured to use claude-3-5-sonnet-20241022 model
- Button icon restoration requires `innerHTML` manipulation (not `textContent`)
- Pinned outputs always auto-size to content; only main output has manual maximize
- Custom names for pinned outputs generate sanitized filenames for downloads