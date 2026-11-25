# Yaydo update file

The Yaydo app reads `update.json` from this repo to decide whether to show its update alert.

- `latest`: the newest version on Google Play. Phones on an older version see "A new Yaydo is ready" (with Later).
- `minimum`: versions below this must update ("Time to update Yaydo", no Later). A new **major** version
  (for example 1.x → 2.0) is always required.
- `android.url`: the store page the alert opens. Only Google Play and App Store links are accepted.
- Optional: `message` (one short plain line shown in the alert), `android.minOs` (lowest Android API
  level the new version runs on; older phones are never blocked).

Release steps: publish the new version on Google Play first, wait until it's live, then edit `latest`
(and `minimum` if older versions must stop) here. The app checks on open and every 6 hours, and
re-checks on every open while an update is required.

Nothing about users is sent: the app makes a plain request for this file.

## Privacy policy

`privacy.html` is the public copy of the in-app privacy policy (Settings › Help and about ›
Privacy policy, `src/app/settings/privacy.tsx` in the app repo), served by GitHub Pages at
https://theahmadraza.github.io/yaydo-updates/privacy.html for the Play listing. Keep the two in step.
