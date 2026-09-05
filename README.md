# Spending Garden PWA

This is a static, local-data Progressive Web App.

## Privacy model
- No analytics, ads, account system, cloud database, remote API, or telemetry is included.
- Categories, purchases, notes, and receipt images are stored locally in IndexedDB on the device/browser.
- The service worker caches only the app's own static files for offline use.
- Data leaves the app only when the user explicitly exports a backup file or otherwise shares a file themselves.

## Install on iPhone/iPad
A PWA must be served from an HTTPS website (a `file://` copy will not install as a true offline web app).
1. Upload this folder unchanged to any static HTTPS host.
2. Open the site in Safari.
3. Tap Share → Add to Home Screen.
4. Enable “Open as Web App” if iOS shows that option, then tap Add.

The static host receives normal web-server request metadata when the app files are downloaded (for example, IP address and browser request headers), but this app does not send your spending records or receipts to the host.

## Local testing on a computer
For service-worker testing, serve the folder from localhost rather than opening `index.html` directly. For example:
`python3 -m http.server 8000`
Then open `http://localhost:8000/`.
