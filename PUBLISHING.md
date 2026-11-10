# Publishing guide — Drawli Terms of Service

These files are prepared for static hosting. No external framework, script, font, or build step is required.

## Structure

```text
drawli-legal/terms/
├── index.html          # English
├── fr/index.html       # French
├── ar/index.html       # Arabic, RTL
└── style.css           # Shared responsive styling
```

## Before publishing

1. Complete every item in `DEVELOPER_CONFIRMATION.md`.
2. Correct the hosted Privacy Policy email link and remove its placeholder notice.
3. Replace every draft notice and unconfirmed legal clause in all three languages.
4. Set one consistent effective date in all pages.
5. Obtain legal and native-language review.
6. Test the English, French, Arabic, privacy, and email links.
7. Verify the Arabic page on a phone and desktop in right-to-left layout.

## Suggested public URLs

If the existing GitHub Pages site is retained, publish at stable URLs such as:

- `https://nexuslabe-debug.github.io/drawli-privacy/terms/`
- `https://nexuslabe-debug.github.io/drawli-privacy/terms/fr/`
- `https://nexuslabe-debug.github.io/drawli-privacy/terms/ar/`

The host should use HTTPS, remain publicly accessible without login, and should not expose an editable document. Keep the URL stable after adding it to Google Play.

## Google Play updates

After publication:

1. Add the Terms URL to the app’s website/support presence where appropriate.
2. Keep the Privacy Policy URL in Play Console and in the app.
3. Re-check App content, Ads, Target audience, Content rating, and Data safety declarations.
4. Make sure the store listing says the app contains ads.
5. Ensure the developer name and contact details match the confirmed legal identity.
6. Do not claim paid features, cloud save, full offline operation, or guaranteed AI accuracy.

Official Google references:

- [Prepare your app for review](https://support.google.com/googleplay/android-developer/answer/9859455?hl=en)
- [User Data policy guidance](https://support.google.com/googleplay/android-developer/answer/10144311?hl=en)

## Live-page verification checklist

- [ ] All three public URLs load over HTTPS without login, geofencing, warnings, or redirects to an editor.
- [ ] The browser reports a valid TLS certificate.
- [ ] English opens at `/terms/`, French at `/terms/fr/`, and Arabic at `/terms/ar/`.
- [ ] Every language-switcher link works from every page.
- [ ] The table-of-contents links scroll to the correct section.
- [ ] Arabic text is right-to-left; the email and technical identifiers remain readable.
- [ ] Pages are readable at 320 px mobile width, common tablet widths, and desktop width without horizontal overflow.
- [ ] The confirmed effective date, publisher identity, governing law, and contact information appear consistently in all languages.
- [ ] The Privacy Policy link opens the correct public policy and its email link works.
- [ ] No draft banner, placeholder, developer note, secret, analytics, tracker, or editable form remains.
- [ ] Page source contains no external JavaScript and no unapproved external dependency.
- [ ] Google Play Console declarations, Data safety answers, store listing, Terms, Privacy Policy, and actual production app behavior agree.
- [ ] A final screenshot or archived copy of each live language page is retained for release records.

## Future maintenance

Review the Terms whenever the app adds accounts, cloud storage, online sharing, new SDKs, new permissions, purchases, subscriptions, server-side AI, or a materially different advertising model. Update the “Last updated” date only when the text actually changes.

