# apps

Landing pages and privacy policies for Shakshi3104's iOS apps, served from GitHub Pages at
**<https://shakshi3104.github.io/apps/>**.

Each app owns a directory with a landing page, a privacy policy, and its assets. The URLs here
are registered in App Store Connect, so **paths must not change once an app has shipped**.

```
/                        hub — iOS Settings-style inset grouped list
/madeleine/              https://github.com/Shakshi3104/Madeleine
/madeleine/privacy/
/yomy/                   https://github.com/minsc-of-secrets/yomy
/yomy/privacy/
/langue-de-chat/         https://github.com/Shakshi3104/LangueDeChat
/langue-de-chat/privacy/
/monaka/                 https://github.com/Shakshi3104/Monaka
/monaka/privacy/
```

## Adding an app

1. Copy an existing app directory and rename it. Keep the directory name lowercase and
   hyphenated — it becomes the public URL.
2. Drop three images into `assets/`:

   | File | Size |
   |---|---|
   | `icon.png` | 1024 × 1024 |
   | `<app>-main-image.png` | 1600 × 1200 |
   | `<app>-og-image.png` | 1200 × 630 |

3. Update the absolute URLs in the `<head>` (`canonical`, `og:url`, `og:image`,
   `twitter:image`) — they are absolute on purpose, since relative URLs break link previews.
4. Add a row to the list in `/index.html`.

## Conventions

- **Privacy pages are `privacy/index.html`**, not `privacy.html`, so the public URL has no
  `.html` extension.
- **Each page carries its own `<style>`.** The app pages deliberately keep their individual
  palettes; there is no shared stylesheet.
- **Dates are `yyyy/MM/dd`.**
- **The hub follows iOS system colors** and adapts to light / dark via `prefers-color-scheme`.
  The app pages are light-only.
- `.nojekyll` keeps GitHub Pages from running the files through Jekyll.

## Local preview

```sh
python3 -m http.server 4321 --bind 127.0.0.1
```

Serve rather than opening the files directly — `file://` does not resolve the directory-style
links (`../`, `privacy/`).
