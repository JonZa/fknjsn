# JSON Formatter

A single-page web application for formatting and managing JSON data.

## Features

- Real-time JSON formatting and validation
- Search and filter JSON content by keys or values
- Pin formatted outputs with custom names
- Download JSON files
- Persistent storage using localStorage
- Copy to clipboard functionality
- Self-contained HTML file with no external dependencies

## Setup

Open `app/index.html` in a web browser. For local development:

```bash
python3 -m http.server 8000
```

Navigate to http://localhost:8000/app/

## Usage

1. Paste or type JSON in the input textarea
2. Formatted output appears in the right panel
3. Use the search box to filter JSON content
4. Pin outputs to save them with optional custom names
5. Download any output as a .json file
6. Copy formatted JSON to clipboard

## Technical Details

- Single HTML file with inline CSS and JavaScript
- Uses localStorage for persistent data storage
- Supports modern browsers with ES6, localStorage, and Clipboard APIs

## File Structure

```
app/
├── index.html          # Main application (self-contained)
├── favicon.ico         # Browser favicon
├── favicon-16x16.png   # 16px favicon
├── favicon-32x32.png   # 32px favicon
├── apple-touch-icon.png # iOS home screen icon
└── icons/              # SVG icons
    ├── copy.svg        # Copy to clipboard
    ├── download.svg    # Download JSON
    ├── maximize.svg    # Maximize textarea
    ├── paperclip.svg   # Pin output
    └── trash.svg       # Remove pinned item
```

## Browser Compatibility

Works in all modern browsers that support:
- ES6 JavaScript
- LocalStorage API
- Clipboard API
- CSS Grid

## License

This project is open source and available for personal and commercial use.