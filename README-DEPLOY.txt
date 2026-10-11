Private hosted PWA deployment
=============================

Recommended host: Azure Static Web Apps with Microsoft Entra authentication.

Files in this folder are the app package:
- index.html
- manifest.webmanifest
- sw.js
- icon.svg
- staticwebapp.config.json

Deployment outline:
1. Create a private GitHub repository, for example trainer-pwa-private.
2. Upload these files to the repository root.
3. In Azure Portal, create a Static Web App.
4. Choose the GitHub repository.
5. Build preset: Custom.
6. App location: /
7. API location: leave blank.
8. Output location: leave blank.
9. Deploy.
10. Open the Azure Static Web Apps URL. It should redirect to Microsoft sign-in.
11. On iPhone Safari, open that HTTPS URL, then Share > Add to Home Screen.

Update workflow:
1. Replace index.html, sw.js, manifest.webmanifest, or icon.svg in the repo.
2. Commit/push.
3. Azure redeploys automatically.
4. iPhone receives the new app shell after reload; local workout data stays in Safari storage.

Privacy note:
Workout logs and body metrics stay in the iPhone browser storage unless you export JSON/CSV.
The hosted app shell contains the training plan and safety constraints, not detailed private medical notes.
