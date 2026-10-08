# LIFE OS — Android PWA starter

This is the first-milestone static app package based on the LIFE OS prototype.

## Included
- `index.html`: mobile-first LIFE OS prototype with schedule screenshot preview and adaptive reminder preference UI.
- `manifest.webmanifest`: install metadata and Android icon declarations.
- `sw.js`: offline app-shell cache and push-event display/click handling scaffold.
- `icons/`: 192px and 512px PNG icons.

## Deploy to test installation
1. Deploy these files together to a public HTTPS static host (for example, a static hosting service).
2. Open the deployed HTTPS URL in Chrome on Android.
3. Use Chrome's **Install app** / **Add to Home screen** option.
4. Test offline launch after the first successful load.

## Important current limitations
- This package does **not** include authentication, cloud sync, scheduled server jobs, a VAPID push sender, Firebase credentials, or an AI API connection. The service worker can display a valid incoming push event, but no service currently sends scheduled pushes.
- Schedule screenshots can be selected and previewed in the UI. Automatic OCR/AI extraction is intentionally not faked; connect a secure AI backend before enabling analysis. For now, confirm shifts with the manual schedule form.
- Existing records remain in browser `localStorage`; they do not sync across devices. Export a backup before clearing browser data.
- The current preview uses rule-based chat, not a live AI model.

## Next backend milestone
Add Supabase Auth and per-user PostgreSQL tables with row-level security; migrate local entries; add a server-side scheduler and push subscription management; then connect screenshot understanding and adaptive notification decisions through a server-side AI endpoint. Keep user-defined quiet hours and confirmed work blocks as hard constraints.
