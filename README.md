# fknjsn

100% client-side JSON formatter, filter, and comparison tool. Your data never leaves your browser.

## Features

- **100% Client-Side** - No server, no uploads, your data stays local
- **JSON Formatting** - Pretty-print and syntax highlight any JSON
- **Live Filtering** - Search/filter JSON by keys or values
- **Side-by-Side Comparison** - Up to 4 JSON blocks per row
- **Dark Mode** - VS Code-inspired theme
- **Persistent Storage** - Saved to localStorage (still local)
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
