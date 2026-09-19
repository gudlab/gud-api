# Gud API

A lightweight, full-featured API client built into your editor. Test REST and GraphQL APIs, organize requests into collections, manage environments, and generate code snippets — without switching to Postman or another external tool.

[![Open VSX](https://img.shields.io/open-vsx/dt/gudlab/gud-api?label=Open%20VSX)](https://open-vsx.org/extension/gudlab/gud-api)
[![VS Marketplace](https://img.shields.io/visual-studio-marketplace/i/gudlab.gud-api?label=VS%20Marketplace)](https://marketplace.visualstudio.com/items?itemName=gudlab.gud-api)

Install from [Open VSX](https://open-vsx.org/extension/gudlab/gud-api) or the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=gudlab.gud-api). Site: [gudapi.gudlab.org](https://gudapi.gudlab.org).

## Source

The **editor extension is proprietary**. This repository is the public home for product docs and [issues](https://github.com/gudlab/gud-api/issues). It does **not** contain the VS Code / Open VSX extension source.

If you followed the GitHub link from the Marketplace or Open VSX, you are in the right place for bugs and feature requests. There is nothing here to clone for the UI.

The companion MCP server **is public**: [`@gudlab/gud-api-mcp`](https://www.npmjs.com/package/@gudlab/gud-api-mcp), source in [gudlab/gud-api-mcp](https://github.com/gudlab/gud-api-mcp). Docs: [gudapi.gudlab.org/guide/ai-agents](https://gudapi.gudlab.org/guide/ai-agents).

## Features

### Request Builder
- All HTTP methods: GET, POST, PUT, PATCH, DELETE, OPTIONS, HEAD
- Query params editor with bidirectional URL sync and enable/disable toggles
- Headers editor with dynamic key-value rows
- Multiple body types: JSON, Form URL Encoded, Multipart Form Data, GraphQL, plain text
- File uploads via multipart form-data with native file picker
- Auth: Bearer Token, Basic Auth, API Key (header or query param)

### GraphQL
- Dedicated GraphQL editor with separate Query and Variables panes
- Auto-sets method to POST and Content-Type to application/json
- Variables parsed as JSON and sent alongside the query

### Response Viewer
- Status code, response time, size, and format detection (JSON/HTML/XML)
- **Pretty / Raw / Preview** toggle — preview renders HTML in a sandboxed iframe
- **Search** — find text in the response body with match count and navigation
- **Cookies tab** — view Set-Cookie headers from the response
- **Copy** button for body or headers

### Code Generation
- Generate code from any request with one click
- Languages: cURL, JavaScript (fetch), Python (requests), Node.js (axios)
- Copy to clipboard

### Request History
- Every request is auto-saved to history (last 100 entries)
- View history in the sidebar with method, URL, status, and timestamp
- Click any entry to reload it into the request builder
- Persists across VS Code sessions

### Cookie Management
- Cookies from responses are automatically captured and stored
- Cookies are auto-sent on subsequent requests to matching domains
- Cookie Manager to view, enable/disable, and delete cookies by domain
- In-memory storage — cookies reset when VS Code restarts

### Collections
- Save and organize requests into collections and folders
- Click to load any saved request back into the builder
- Right-click to rename, delete, or create new folders
- Supports deeply nested folder structures

### Import
- Postman v2.x collections (including nested folders, headers, body, and collection variables)
- Thunder Client collections
- OpenAPI 3.x / Swagger 2.0 specs (paths become requests, tags become folders)
- Import via sidebar button or command palette

### Environments & Variables
- `{{variable}}` syntax in URLs, headers, and body — resolved automatically on send
- Collection-level variables imported from Postman (e.g. `{{base_url}}`)
- User-defined environments with key-value editor and enable/disable toggles
- Environment selector in the toolbar — switch between environments instantly
- Variable resolution order: environment overrides collection variables

### Editor Integration
- Activity bar icon for quick access
- Matches your VS Code theme automatically (light, dark, high contrast)
- Works without a workspace open (stores in VS Code global storage)
- Keyboard shortcut: Enter to send request

## Getting Started

1. Install the extension from Open VSX or the VS Code Marketplace
2. Click the **Gud API** icon in the activity bar
3. Enter a URL and press **Send**
4. Click **Save** to add the request to a collection

To import an existing collection, click **Import** in the sidebar and select a Postman, Thunder Client, or OpenAPI JSON file.

## MCP for AI agents

Agents can create, run, and save requests as real Gud API collections via `@gudlab/gud-api-mcp`:

```json
{
  "mcpServers": {
    "gud-api": {
      "command": "npx",
      "args": ["-y", "@gudlab/gud-api-mcp", "--project", "."]
    }
  }
}
```

Source and tools: [gudlab/gud-api-mcp](https://github.com/gudlab/gud-api-mcp). Guide: [gudapi.gudlab.org/guide/ai-agents](https://gudapi.gudlab.org/guide/ai-agents).

## Free vs Pro

Gud API is free to use with no limits on requests, collections, or folders. Team / cloud sync is the Pro upsell.

| Feature | Free | Pro |
|---------|------|-----|
| Unlimited requests | Yes | Yes |
| Collections & folders | Yes | Yes |
| Import (Postman, Thunder Client, OpenAPI) | Yes | Yes |
| Auth (Bearer, Basic, API Key) | Yes | Yes |
| GraphQL support | Yes | Yes |
| Multipart form-data & file upload | Yes | Yes |
| Code generation (cURL, fetch, Python, axios) | Yes | Yes |
| Request history | Yes | Yes |
| Cookie management | Yes | Yes |
| Response search & format toggle | Yes | Yes |
| Collection variables | Yes | Yes |
| Environments | 1 | Unlimited |
| Team sync | - | Yes |
| Cloud collections | - | Yes |

**Pro**: $4/month or $29 lifetime.

## Support

Gud API is free with no limits. If it saves you time, consider supporting development:

- [Buy Me a Coffee](https://buymeacoffee.com/timchosen)
- [PayPal](https://paypal.me/timchosen)

## Feedback & Issues

Report bugs or request features at [github.com/gudlab/gud-api/issues](https://github.com/gudlab/gud-api/issues).

## License

Proprietary. See [LICENSE](./LICENSE). The editor UI is not open source. The MCP server has its own license in [gudlab/gud-api-mcp](https://github.com/gudlab/gud-api-mcp).
