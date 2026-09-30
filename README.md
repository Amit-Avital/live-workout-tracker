# Live Workout Tracker website

Public website: https://amit-avital.github.io/live-workout-tracker/
Privacy policy: https://amit-avital.github.io/live-workout-tracker/privacy/

Only public website content belongs in this repository. The native app source remains in the separate private set-tracker repository.

## Files and local preview

- `index.html`: homepage and minimal product introduction.
- `privacy/index.html`: policy text; edit this single canonical document.
- `assets/styles.css`: shared layout, light/dark palettes, typography, and print styles.
- `assets/app-icon.png`: existing app icon, also used as the favicon.
- `.nojekyll`: serve these files directly with no generator.

Run `python3 -m http.server 8080` here and open http://localhost:8080/ . Also check from a parent folder at `/live-workout-tracker/` to verify project-path hosting. No package installation or build is needed.

## Publish and maintain

GitHub Settings → Pages: Deploy from a branch, `main`, `/ (root)`, with HTTPS enabled. Pushing to main publishes changes. Verify both URLs without signing in after each deployment. Do not delete or relocate `/privacy/`; released apps link to it.

Policy edits must reflect shipped app behavior. Check Health permissions, local storage, paired-device transfers, SDKs, and deletion controls before changing claims. Update the effective date for changes in privacy practices; Git retains previous versions. Do not add analytics, remote fonts, forms, or third-party embeds without reviewing their privacy impact and updating the policy. Keep support-email retention aligned with the policy.

## Extend the template

Use the existing header, navigation, footer, `.intro`, and section patterns for new content. Keep shared colors, fonts, spacing, and widths in CSS variables. Add screenshots under `assets/screenshots/` with descriptive alt text and intrinsic dimensions; responsive images should use `max-width: 100%; height: auto`. Add a gallery or feature section between the introduction and privacy note when real content is ready. Keep the Privacy Policy link visible.

Replace the icon and CSS design tokens when branding changes. Update the matching shared header/footer markup in both HTML files. Add an App Store button only after there is a verified public listing; use Apple's official badge assets and usage guidance. There are no unpublished or empty marketing sections.

For new pages, copy the document shell, use one h1, set a unique title/description/canonical URL, and adjust relative asset and navigation paths. Current relative paths work under the GitHub project prefix and a custom-domain root.

## Custom domain migration

Configure the domain in GitHub Pages, add its CNAME and DNS records following GitHub's instructions, enable HTTPS, and update canonical URLs. Verify `/privacy/` at both old and new addresses. Preserve the existing GitHub Pages URL/redirect for installed app versions; update the native app constant and App Store Connect URLs only after the new route is publicly working. Do not rename the repository or remove old routing while released apps depend on it.

## Release checks

Check phone and desktop layouts, keyboard focus, text enlargement, print layout, all internal links, and anonymous HTTPS access. All page resources should be same-origin; no JavaScript or tracking is included. In App Store Connect use `/privacy/` as the Privacy Policy URL and the homepage as Support/Marketing URL. Review the app privacy questionnaire separately from the website's hosting disclosure.
