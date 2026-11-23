# Snake Trap website (privacy, terms, account deletion, app-ads.txt)

Static pages for the Play listing. Nothing here is built into the app.

| File | Use it for |
| --- | --- |
| `index.html` | Developer website on the Play listing (needed for app-ads.txt) |
| `privacy.html` | Play Console → App content → Privacy policy; app `EXPO_PUBLIC_PRIVACY_POLICY_URL` |
| `terms.html` | app `EXPO_PUBLIC_TERMS_URL` |
| `delete-account.html` | Play Console → App content → Data deletion URL |
| `app-ads.txt` | Must be at the site root: `https://<site>/app-ads.txt` |

## Fill in before publishing

Search and replace in all `.html` files:

- `{{STUDIO_NAME}}`: your name or studio name, as shown on the Play listing (e.g. "Pixelora Studio")
- `{{SUPPORT_EMAIL}}`: the support email on the Play listing
- `{{EFFECTIVE_DATE}}`: e.g. "23 November 2026"
- `{{COUNTRY}}`: your country (and state if relevant), e.g. "India"
- `{{YEAR}}`: e.g. "2026"

## Publish free with GitHub Pages

1. On github.com create a **public** repository named `<your-username>.github.io`
   (the site then lives at `https://<your-username>.github.io/`, with app-ads.txt at the root).
2. Upload every file in this folder (Add file → Upload files), commit.
3. Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
4. After a minute, open `https://<your-username>.github.io/privacy.html` to check.
5. Use these URLs:
   - Privacy: `https://<your-username>.github.io/privacy.html`
   - Terms: `https://<your-username>.github.io/terms.html`
   - Account deletion: `https://<your-username>.github.io/delete-account.html`
   - Developer website (Play listing): `https://<your-username>.github.io/`
6. Set the app links on EAS and rebuild:
   `npx eas-cli env:create --environment production --name EXPO_PUBLIC_PRIVACY_POLICY_URL --value <privacy url> --visibility plaintext`
   `npx eas-cli env:create --environment production --name EXPO_PUBLIC_TERMS_URL --value <terms url> --visibility plaintext`

Google Sites or any static host works too, as long as app-ads.txt is served at the root.
