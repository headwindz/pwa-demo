# PWA Service Worker Demo

A minimal Progressive Web App demo that shows how to register a service worker, pre-cache core assets, and use a cache-first strategy for fetch requests.

## Features

- Registers a service worker on page load.
- Pre-caches core assets:
  - `index.html`
  - `app.js`
  - `app.css`
- Cleans up old caches on activation.
- Uses cache-first fetch handling with network fallback.
- Includes a test button that fetches sample JSON data and logs results to the page.

## Project Structure

- `index.html` – Simple UI with a test button and log output.
- `app.js` – Service worker registration + fetch test logic.
- `serviceWorker.js` – Install/activate/fetch event handlers and cache logic.
- `app.css` – Basic layout and log panel styles.

## Run Locally

`http-server` is a simple, zero-configuration command-line HTTP server. You can install it globally using npm:

```bash
npm install -g http-server
```

1. Clone the repository or download the source code.
2. Navigate to the project directory in your terminal.
3. Start the server with the following command:

```bash
 http-server -p 8080 
```

4. Open your browser and go to `http://localhost:8080` to see the app in action.

## How to Test

- Open `DevTools` → `Application` → `Service Workers`: should show registered
- Open `Application` → `Cache`: should see `app-v1` with cached assets
- Click "Test Fetch": should log network request
- Enable `Network` → `Offline` in DevTools
- Click "Test Fetch" again: should show `offline` message
- Refresh page while `offline`: cached page still loads

