# KimiaPro KPI Tracker - App Package

This package converts your KPI tracker HTML tool into a Capacitor-based mobile app project.

## What is included
- `www/` - packaged web app used by iPhone/Android shells
- `ios/` - generated iOS Capacitor project
- `android/` - generated Android Capacitor project
- `resources/icon-1024.png` - starter app icon
- `capacitor.config.ts` - app configuration
- `manifest.webmanifest` + `service-worker.js` - PWA preview/offline shell

## Preview right away
### Option A - Quick browser preview on computer
1. Extract the zip.
2. Open a terminal in the extracted folder.
3. Run:
   ```bash
   npm install
   npm run serve
   ```
4. Open `http://localhost:4173` in your browser.

### Option B - Preview on iPhone without a Mac
1. Upload the `www` folder contents to a simple static host such as GitHub Pages / Netlify / Cloudflare Pages.
2. Open the hosted URL in Safari on your iPhone.
3. Tap **Share > Add to Home Screen**.

This gives you a PWA-style preview that feels app-like and works offline after first load.

## iPhone App Store path (without owning a Mac)
### Cloud-build route
Use a Capacitor-compatible cloud build service such as Ionic Appflow.

Suggested flow:
1. Put this project in a Git repository.
2. Connect the repository to Ionic Appflow.
3. Create an iOS native build in Appflow.
4. Upload the resulting build to App Store Connect.
5. Submit to TestFlight / App Review.

## Local Mac route
If you later get temporary access to a Mac:
```bash
npm install
npx cap sync
npx cap open ios
```
Then complete signing, icons, bundle settings, archive, and upload in Xcode.

## Important packaging notes
- Chart.js has been bundled locally in `www/assets/chart.umd.js` so the app does not depend on a remote CDN script.
- Local browser storage is used for project saves. In the iOS app, those saves stay on the device unless you build cloud sync later.
- The current PDF/export behavior remains browser-based HTML export. If you want a more native iPhone share/export flow later, add Capacitor Share and Filesystem plugins.

## Recommended next actions before submission
- Replace the starter icon with your final branded icon.
- Add App Store screenshots.
- Test import/export on iPhone Safari and in the final app shell.
- Decide whether the first release is paid on the App Store, free, or free with Gumroad code access.
