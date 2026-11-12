# HVAC AI Copilot — Installable iPhone PWA (v0.2)

This is a **working offline-capable, simulated training demo**, not a connected generative-AI product. It has equipment entry, simulated technician conversation, optional browser speech recognition, spoken responses via browser speech synthesis, a service report, and device-local session persistence.

## Publish to an HTTPS URL (recommended: GitHub Pages)
1. Extract the ZIP file.
2. Create a **new public GitHub repository** (e.g. `hvac-copilot-demo`). Do not upload private customer records or credentials.
3. Upload **the contents of** `hvac-copilot-ios-pwa/` to the repository root, including `index.html`, `app.js`, `styles.css`, `manifest.webmanifest`, `service-worker.js`, and the `icons` folder.
4. In GitHub: **Settings → Pages → Build and deployment → Deploy from a branch**, select `main` and `/ (root)`, then save.
5. After deployment, open the HTTPS Pages URL (usually `https://YOUR-USERNAME.github.io/hvac-copilot-demo/`) on the iPhone in **Safari**. The actual URL depends on your repository settings.
6. Tap **Share → Add to Home Screen → Add**. Open **HVAC Copilot** from the Home Screen.
7. First load requires internet; after the service worker caches files, the simulated demo works offline. Speech features depend on iOS/browser availability and may require connectivity.

## Voice interaction on iPhone
- Tap **Voice off** to enable spoken responses (uses speech synthesis, where available).
- Tap the 🎙 button to dictate when the browser supports the Web Speech recognition API and grants permission.
- If the mic button is disabled or unavailable, tap the message field and use the **microphone on the iOS keyboard** to dictate, then tap Send. iOS keyboard dictation is controlled by the device, not the app.
- Test microphone and speech playback on the actual iPhone; support varies across iOS versions and browser contexts.

## Local testing
From the extracted directory on Windows, run `py -m http.server 8000` and visit `http://localhost:8000` on your computer. Installing on an iPhone requires an HTTPS deployment; a local desktop HTTP server is not sufficient for iPhone installation/testing.

## Data and safety
- This version is **scripted**, not connected to OpenAI or OEM documentation. It does not validate equipment models or fault codes.
- Session content is saved in **localStorage on the device**. Reset clears it. Do not enter customer names, addresses, secrets, or sensitive job details. Clearing browser/site data can remove the session.
- The app is a **training demonstration only**. Do not use it to guide live electrical, refrigerant, combustion, or other hazardous repair work.
- Do not put OpenAI API keys into `app.js` or any browser-distributed file. A future AI-connected version needs a secure backend.
- The demo is not authenticated. A public GitHub Pages site is accessible to anyone with the URL and should contain no confidential information.

## Next milestone
Secure backend + authenticated access, server-side OpenAI API, authorized OEM manual ingestion with exact equipment-model filtering and citations, technician-reviewed evaluation suite, and supervised pilot.
