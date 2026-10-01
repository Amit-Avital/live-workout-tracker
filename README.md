# Live Workout Tracker website

Public website: https://amit-avital.github.io/live-workout-tracker/
Privacy policy: https://amit-avital.github.io/live-workout-tracker/privacy/
Contact: https://amit-avital.github.io/live-workout-tracker/contact/

Only public website content belongs in this repository. The native app source remains in the separate private set-tracker repository.

## Files and local preview

- `index.html`: homepage and minimal product introduction.
- `contact/index.html`: support form; forwards to lp4company@gmail.com using FormSubmit.
- `contact/thanks/index.html`: submission acknowledgement after FormSubmit processing.
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

Replace the icon and CSS design tokens when branding changes. Update the matching shared header/footer markup in every HTML page. Add an App Store button only after there is a verified public listing; use Apple's official badge assets and usage guidance. There are no unpublished or empty marketing sections.

For new pages, copy the document shell, use one h1, set a unique title/description/canonical URL, and adjust relative asset and navigation paths. Current relative paths work under the GitHub project prefix and a custom-domain root.

## Custom domain migration

Configure the domain in GitHub Pages, add its CNAME and DNS records following GitHub's instructions, enable HTTPS, and update canonical URLs. Verify `/privacy/` at both old and new addresses. Preserve the existing GitHub Pages URL/redirect for installed app versions; update the native app constant and App Store Connect URLs only after the new route is publicly working. Do not rename the repository or remove old routing while released apps depend on it.

## Release checks

Check phone and desktop layouts, keyboard focus, text enlargement, print layout, all internal links, and anonymous HTTPS access. All page-load resources are same-origin; no JavaScript or tracking is included. Form submissions POST to FormSubmit; verification happens on its site. In App Store Connect use `/privacy/` as the Privacy Policy URL and the homepage as Support/Marketing URL. Review the app privacy questionnaire separately from the website's hosting disclosure.

## Contact form delivery

All Support, Contact support, and email-address links lead to `/contact/`.
The form uses a native HTTPS POST to `https://formsubmit.co/lp4company@gmail.com`.
It requires a reply email and a 10–5,000-character message; name is optional.
The email input becomes Reply-To. reCAPTCHA remains enabled, with a honeypot
as an additional spam filter. No API key or inbox credential is exposed.

FormSubmit sends a one-time activation email to the receiving inbox. The owner
must activate the form before normal delivery works. Until then, FormSubmit holds
submissions (documented retention: 30 days). Verify an actual test message arrives
after activation, including its Reply-To, before treating delivery as confirmed.
Use only nonsensitive test content. Provider errors remain on FormSubmit's page;
visitors can go back to the form. No JavaScript assumes success after a timeout.

The contact page uses `strict-origin-when-cross-origin` so FormSubmit can verify
the sending website; other pages retain `no-referrer`. `_url` explicitly identifies
the contact page without including visitor-entered data.
`_next` returns to the full HTTPS `/contact/thanks/` address after processing.
Keep these values current if the site moves. Do not disable spam verification.
The thank-you page acknowledges submission, not guaranteed inbox delivery.

The privacy policy discloses FormSubmit, its 30-day submission archive, Google
reCAPTCHA, and Gmail. Re-review that policy when changing the form provider or
collecting more information. Do not add uploads or automatically attach workout
records. App data collection is unchanged: this is a voluntary external web form.

Provider documentation: https://formsubmit.co/documentation
Activation help: https://formsubmit.co/help
