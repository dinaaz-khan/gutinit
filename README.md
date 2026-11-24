# Neighbr

**Better Spaces. Better Communities.**

Neighbr is a responsive, interactive frontend prototype for community water-leak reporting and repair coordination. It uses realistic seeded records and browser storage so the full workflow can be demonstrated without external credentials.

## Run locally

```bash
npm install
npm run dev
```

Create a production build with `npm run build`.

## Demo flow

The app opens on the public landing page. Select **Explore dashboard** to enter the workspace. Use the role selector in the dashboard header to switch between **Resident**, **Administrator**, and **Maintenance** views.

- **Resident:** Riya’s open washroom-tap report is already in progress. Open it to follow the status timeline, or submit a new report with a photo.
- **Administrator:** Review all reports, filter by status and severity, open details, change priority, assign a teammate, and edit the water-loss estimate.
- **Maintenance:** Open **My tasks**, start a repair, add repair notes and an after-repair photo, update the estimate, then mark the repair resolved.

New reports and updates persist in `localStorage` under `neighbr-complaints`. Clear that browser storage to restore the original demo data.

## Prototype boundaries

Authentication is a role selector for demonstration; no real credentials are required. Photo uploads are previews stored in browser state. There is no connected Express API, MongoDB Atlas database, Cloudinary account, JWT session, or bcrypt password service in this frontend-only prototype.

The current complaint shape in `src/App.tsx` is a useful starting point for an API model. A future backend can expose user, complaint, repair-request, and status-history collections and replace the local storage helpers with API calls. The UI already keeps reported estimates separate from sensor data.

Future ideas, outside this MVP, include IoT leak detection, QR reporting, push notifications, predictive maintenance, and additional issue categories.
