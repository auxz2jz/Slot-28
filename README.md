# Patrol Geofence Lab v0.1

Standalone mobile-friendly prototype for pin-based patrol site mapping and GPS-assisted report selection. This repository is public. Do not commit real boundary exports, officer reports, schedules or GPS logs.

## Run

Enable GitHub Pages in Settings → Pages → Build and deployment → Deploy from a branch → main / (root), then open https://auxz2jz.github.io/Slot-28/. Alternatively download index.html and serve it from an HTTPS origin or localhost; live GPS requires a secure browser context and permission. Internet is needed for Leaflet, real map imagery and address lookup.

## Practice mode

1. Tap Tap map to simulate GPS, then tap inside a colored polygon.
2. Tap Start new report; see automatic selection when the accuracy circle fits in one boundary, or manual choice when uncertain.
3. Try between Rhino Market and Rancho San Miguel and increase the accuracy radius.
4. Choose Edit / draw boundary, tap to add pins, drag to reposition, tap a pin to delete, Undo if needed, Save boundary. Start new outline clears the working draft.
5. Save a sample report and export the JSON if desired.

Practice geometry is fictional and independent of real map mode. Real mode preloads four site names and address hints only; select each site, Find address, visually verify it, draw the actual contracted area, and save. Rhino and Rancho share an address hint from prior site data; verify the exact patrol areas. Actual coverage boundaries are intentionally not published. Real mode supports phone GPS and simulated map positions; simulated positions are explicitly labeled in the report. Switch modes to reset position or use phone GPS to return to live readings.

## Data and limits

Boundaries and sample reports are stored locally per mode; exports are JSON files. No company server, background tracking, submission, account controls or production integration. Map providers and public address geocoding are third-party dependencies. Each site currently supports one simple polygon, with a maximum of 1000 vertices; multiple regions and exclusions are future work. Position classification uses point-in-polygon and local meter-distance to nearest edge. Auto selection is allowed only if one candidate contains the reported accuracy circle and reported accuracy is no more than 45 m. GPS uncertainty is not guaranteed; confirm close boundaries with field tests. Manual override is always available.

## Validation

JavaScript syntax and isolated geometry checks passed for an interior position, ambiguity between adjacent polygons, outside all polygons, and rejecting a crossing polygon. Browser rendering, external services, GPS permission and actual field accuracy still require device testing.
