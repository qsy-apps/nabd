# Legal pages for Google Play (QSY / Nabd)

These static pages satisfy Google Play requirements for **Privacy Policy** and **Terms of Service**.

## Files

| File | Use in Play Console |
|------|---------------------|
| `privacy-policy.html` | **Privacy policy URL** (required) |
| `terms-of-service.html` | Optional; linked from app |
| `index.html` | Landing page |

## Host the pages

Upload the entire `legal/` folder to any public HTTPS host, for example:

- **GitHub Pages** — create repo `nabd-legal`, enable Pages from `/legal` or root
- **Firebase Hosting** — `firebase deploy` with `public: legal`
- **Your domain** — e.g. `https://nabd.app/legal/privacy-policy.html`

Then update `lib/core/legal/legal_config.dart`:

```dart
static const policyBaseUrl = 'https://YOUR-DOMAIN/legal';
```

## Google Play Console

1. **App content → Privacy policy** — paste:
   - Arabic default: `https://YOUR-DOMAIN/legal/privacy-policy.html?lang=ar`
   - Or English: `...?lang=en`

2. **Data safety form** — declare at minimum:
   - Location (approximate) — for matching / country display
   - Personal info — email, username, photos, gender
   - Messages — user-generated content
   - Device IDs — AdMob advertising

3. **Contact email** — set `support@qsy.dev` (or your real support inbox) in Store listing and update `LegalConfig.supportEmail`.

## In-app

- Register screen requires accepting Terms + Privacy
- Profile → Legal links
- Welcome screen footer links

Developer name on Play: **QSY**
