# iosphotobackup

The public site for the PhotoBackup iOS app: privacy policy and support page,
which the App Store requires as live public URLs.

**This repository contains the website only.** The app's source lives
elsewhere, in a private repository, and nothing here exposes it.

## Publishing

GitHub Pages serves this straight from the default branch — there is no build
step, and no dependencies.

1. On github.com, create a **public** repository named `iosphotobackup`.
2. From this folder:

   ```
   git init
   git add -A
   git commit -m "Privacy policy and support pages"
   git branch -M main
   git remote add origin git@github.com:JChaCreates/iosphotobackup.git
   git push -u origin main
   ```

3. In the repository: **Settings → Pages → Source: Deploy from a branch →
   `main` / `/ (root)`**.

Live within a minute or two at:

- `https://jchacreates.github.io/iosphotobackup/privacy.html`
- `https://jchacreates.github.io/iosphotobackup/support.html`

## Using jchacreates.com instead

Worth doing, since the domain already exists — these URLs appear on the App
Store listing, and a real domain reads as a going concern rather than a
side project.

1. Add a `CNAME` file to this repository containing one line, e.g.
   `photobackup.jchacreates.com`.
2. At the DNS provider, add a CNAME record for that subdomain pointing at
   `jchacreates.github.io`.
3. Settings → Pages → Custom domain, then tick **Enforce HTTPS** once the
   certificate is issued.

Do this *before* submitting to App Store Connect if you intend to at all.
Changing the URL later means editing store metadata, and any link already in
the wild breaks.

## Keeping it honest

The privacy policy makes specific claims: no analytics, no networking outside
StoreKit, sidecars written beside the photos, database excluded from iCloud
backup. Those are all true of the app today. If any of them stops being true,
this file has to change in the same release — a privacy policy that has
quietly drifted is worse than not having written one.

## Note

The repository is public, so its whole history is public. Only site files
belong here: no screenshots of client work, no notes, no scratch files. A
later `git rm` does not remove anything from history.
