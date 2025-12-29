# Obsicard - Trello Power-Up for Obsidian Links

A custom Trello Power-Up that detects Obsidian note URLs (`obsidian://`) when pasted as card attachments and displays them as clickable links that open directly in Obsidian.

## Features

- Automatically detects Obsidian URLs (`obsidian://`) when added as card attachments
- Displays a styled clickable button in the attachment section
- Opens the note directly in Obsidian when clicked

## Setup

### Prerequisites

- A web server with HTTPS (required by Trello)
- For local development, use a tool like [ngrok](https://ngrok.com/) to expose your local server

### Installation

1. Host the Power-Up files on a web server with HTTPS enabled
2. Register your Power-Up in the [Trello Power-Up Admin Portal](https://trello.com/power-ups/admin)
3. Enable the Power-Up on your Trello board

### Local Development

1. Start a local web server (e.g., using Python):
   ```bash
   python3 -m http.server 8000
   ```

2. Expose your local server using ngrok:
   ```bash
   ngrok http 8000
   ```

3. Use the HTTPS URL provided by ngrok when registering your Power-Up

## Usage

1. Open a Trello card
2. Add an attachment by pasting an Obsidian URL (e.g., `obsidian://open?vault=MyVault&file=MyNote`)
3. The Power-Up will automatically detect the Obsidian URL and display a clickable "Open in Obsidian" button
4. Click the button to open the note in Obsidian

## Obsidian URL Format

Obsidian URLs follow this format:
```
obsidian://open?vault=VaultName&file=NoteName
```

Make sure to URL-encode special characters:
- Spaces: `%20`
- Forward slashes: `%2F`
- Other special characters as needed

## Files

- `manifest.json` - Power-Up manifest configuration
- `index.html` - Main Power-Up initialization and attachment detection
- `attachment-section.html` - UI for displaying the Obsidian link
- `package.json` - Project configuration
- `icon.svg` - Power-Up icon (SVG icon included)

## Development

The Power-Up uses Trello's Power-Up JavaScript library, which is loaded via CDN. No build process is required for basic functionality.

## License

MIT

