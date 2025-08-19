# JSON Formatter

A clean, fast, and feature-rich JSON formatter web application with persistent storage.

## Features

- **Real-time Formatting** - Automatically formats JSON as you type or paste
- **Error Handling** - Clear error messages for invalid JSON
- **Pin Outputs** - Save multiple formatted JSON outputs with custom names
- **Persistent Storage** - Pinned outputs are saved to localStorage and persist across sessions
- **Download JSON** - Export formatted JSON as downloadable files
- **Maximize View** - Expand textareas to fit content perfectly
- **Icon-based UI** - Clean, intuitive interface with SVG icons
- **Fully Offline** - No external dependencies, works completely offline

## Usage

1. **Open the app** - Simply open `app/index.html` in your browser
2. **Paste JSON** - Paste or type JSON in the left textarea
3. **View formatted output** - Formatted JSON appears instantly on the right
4. **Pin outputs** - Click the pin button to save outputs with optional custom names
5. **Download** - Export any output as a `.json` file

## Development

Run a local server:
```bash
python3 -m http.server 8000
```

Then navigate to http://localhost:8000/app/

## Technical Details

- **Zero Dependencies** - Single HTML file with inline CSS and JavaScript
- **LocalStorage** - Persistent storage for pinned outputs
- **Responsive Design** - Works on desktop and mobile devices
- **Modern Browser Support** - Uses native clipboard API and modern JavaScript

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