# Overview
Local API POST Tester is a lightweight, single-file web app to quickly send POST (and other) HTTP requests to your local API and inspect responses. It supports custom headers, JSON body authoring with formatting tools, timeouts, credentials/mode controls, response pretty-printing, cURL export, file drop for request bodies, and local presets.

# Setup
No build tools required.

Option A: Open directly
- Save index.html to your machine.
- Double-click to open in your browser.
- Note: When opened via file://, your local API must allow CORS from file origins or you should run this page from the same origin as your API.

Option B: Serve locally (recommended for CORS)
- From the folder containing index.html, run a simple static server, e.g.:
  - Python: python3 -m http.server 8080
  - Node (http-server): npx http-server -p 8080
- Visit http://localhost:8080 and use the app. This reduces CORS issues when testing APIs on the same origin/port.

# Usage
1. Enter your API URL (e.g., http://localhost:3000/api/endpoint).
2. Choose HTTP method (default POST).
3. Add headers if needed. Content-Type: application/json is added automatically for JSON bodies.
4. Compose the request body:
   - Type JSON or raw text.
   - Use Format/Minify to tidy JSON.
   - Drag-and-drop a .json/.txt file or use the file picker to load content.
5. Adjust timeout, credentials, and request mode if necessary.
6. Click Send Request (or press Ctrl/Cmd+Enter).
7. Inspect the Response panel:
   - Status, time, size, headers, and body.
   - Toggle Pretty for JSON, copy body/headers, or download the body.
8. Optional utilities:
   - Copy as cURL for terminal usage.
   - Save your current setup as a preset and reload it later.

Troubleshooting:
- CORS errors: Configure your local server to allow the origin of this page, or run the page from the same origin and port as the API.
- Timeouts: Increase the Timeout (ms) value if your API is slow to respond.
- Opaque responses: Avoid no-cors mode unless necessary; it prevents reading the response body.