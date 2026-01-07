# fknjsn

A JSON comparison tool. Paste JSON, compare side-by-side, search within blocks.

## Features

- **Row/Column Layout** - Compare up to 4 JSON blocks per row
- **Live Search** - Filter JSON by keys or values within each block
- **Dark Mode** - VS Code-inspired theme
- **Persistent Storage** - Rows and data saved to localStorage
- **No Build Step** - Single HTML file, CDN dependencies

## Usage

1. Click a row to select it
2. Paste JSON (auto-fills first empty column or creates new)
3. Use search box to filter within each block
4. Click "+" to add more columns (max 4)
5. Click "×" to remove rows or columns

## Setup

```bash
python3 -m http.server 8000
```
Open http://localhost:8000/app/

## Tech Stack

- Vue 3.4.21 (CDN)
- vue-json-pretty 2.4.0 (CDN)
- CSS Custom Properties for theming
- localStorage for persistence

## File Structure

```
app/
├── index.html      # Complete application
├── favicon.ico
├── favicon-16x16.png
├── favicon-32x32.png
└── apple-touch-icon.png
```
