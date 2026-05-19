# assistantrio.com

Static landing page. One file, four images. No build step, no dependencies.

## Files

```
index.html                    Landing page. Inline CSS, no JS, no external requests.
rio-mark.png                  Light-mode brand mark. 2048×2048, transparent.
rio-mark-reversed.png         Dark-mode brand mark. 2048×2048, transparent.
rio-favicon.png               Light-mode favicon. 512×512, solid warm-bone bg.
rio-favicon-reversed.png      Dark-mode favicon. 512×512, solid warm-dark bg.
CNAME                         GitHub Pages custom-domain binding.
```

All five referenced files must sit at the repo root. The HTML uses relative paths — no folder restructuring without updating `<img src>` and `<link rel="icon">`.

## Deploy

1. Create a new repo. Push these files to the default branch root.
2. Settings → Pages → Source: deploy from branch, `/ (root)`.
3. Settings → Pages → Custom domain: `assistantrio.com`. Save.
4. At the domain registrar, add either:
   - `ALIAS` / `ANAME` on the apex pointing to `<user>.github.io`, or
   - four `A` records on the apex pointing to GitHub Pages' IPs:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - and a `CNAME` on `www` pointing to `<user>.github.io`.
5. Back in Settings → Pages, tick **Enforce HTTPS** once the cert provisions (5–15 min).

## What it does

- Light and dark mode swap automatically via `prefers-color-scheme`. No toggle.
- Mark image swaps via CSS `content:` rule; favicon swaps via paired `<link>` with `media=`.
- `noindex, nofollow` meta + `no-referrer` keeps the page out of search results and stops outbound referer headers.

## Page weight

~110 KB total: HTML 4 KB, four PNGs roughly 25 KB each. No webfonts, no analytics, no JS.

## To edit copy

Open `index.html`. The quote, attribution, description, and footer line are all in plain markup near the bottom of the file. Change in place — no rebuild needed.
