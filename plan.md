# EventSponsor Uganda — implementation plan

## Product outcome
A polished responsive MVP for a Uganda-focused sponsorship marketplace connecting verified event organizers and brands. The site should make discovery, matching, trust, proposal-building, workflow management, and ROI reporting feel concrete while clearly labeling demo-only workflows and sample data.

## Architecture
- Vite + React single-page frontend with client-side view state for the demo experience.
- Static delivery: the initial page contains meaningful marketplace copy and public event data; no backend, auth, payments, or live matching are claimed as complete.
- `/manus-routes.json` declares the current public route `/`.
- No server or database configured in this stage; dynamic-looking panels use local sample data and controlled interactions.

## UI structure
- `src/main.jsx`: app shell, sample marketplace data, navigation, filters, event detail modal, matching, proposal builder, ROI and admin preview panels.
- `src/styles.css`: responsive visual system, layout, cards, charts, accessibility states, mobile adaptations.
- `public/manus-routes.json`: route manifest.
- `ideas.md`: chosen visual direction and brand system.

## Delivery and caching
Static SPA output is the best fit for this public, demo-first MVP. Build output is `dist`; versioned assets can be long-lived while HTML remains revalidated by the hosting layer. No API route or personalized response exists in this stage.

## Verification
Use `npm run build`, inspect the output, start the Vite dev server on the configured port, request `/` and `/manus-routes.json`, and confirm the manifest is valid JSON and the app returns HTTP 200. Use source inspection for accessibility labels, responsive CSS, and explicit demo-state wording.
