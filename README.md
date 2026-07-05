# Ernie — Photography & Design (portfolio site)

A static, no-build-tools portfolio site. Plain HTML/CSS/JS, so it runs directly on GitHub Pages with zero configuration.

## Design concept

Dark, moody, built around the vernacular of analog photography: film-frame numbers (`NO. 01`, `NO. 02`...) instead of generic section numbering, a running sprocket-hole rail down the left edge, and EXIF-style mono captions (`f/2.8 · 1/250 · ISO 400`) under photography frames. The "contact sheet" work grid is the signature element — it's meant to feel like reviewing negatives, not browsing a template.

Palette: near-black background, warm off-white text, brass/gold as the primary accent, a deep safelight-red used sparingly for frame numbers.

Fonts: Fraunces (display headlines), Public Sans (body copy), JetBrains Mono (labels, EXIF captions, frame numbers) — loaded from Google Fonts in `index.html`.

## File structure

```
index.html        — all page content and structure
css/style.css      — full design system (tokens at the top of the file)
js/main.js         — mobile nav toggle + work-filter logic
images/            — put your real photos/graphics here
```

## Deploying to GitHub Pages

1. Create a new repository on GitHub (e.g. `your-username.github.io` for a root domain, or any name like `portfolio`).
2. Push these files to the repo (root of the repo, not a subfolder — unless you're fine with a `/portfolio` URL path).
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to "Deploy from a branch," branch `main`, folder `/ (root)`.
5. Save. GitHub will give you a URL like `https://your-username.github.io/portfolio/` within a minute or two.

If you named the repo `your-username.github.io`, the site will live at `https://your-username.github.io/` directly.

## Customizing content

**Swap in real images**
Every image is currently a placeholder block (striped pattern + label showing the suggested dimensions). To replace one:
1. Drop your image file into `/images`.
2. Find the matching `<div class="placeholder-img ...">...</div>` in `index.html`.
3. Replace it with an `<img src="images/your-file.jpg" alt="describe the image" class="[same classes]">`.

**Update the work grid**
Each project is one `<article class="frame" data-category="...">` block in the `#contact-sheet` section. `data-category` must be `photo`, `graphic`, or `web` to work with the filter buttons. Copy an existing block to add a new project; delete one to remove a project.

**Contact email**
Change the address in the `mailto:` link in the Contact section (`index.html`, search for `hello@example.com`) and update the social links (`href="#"` placeholders) to your real Instagram/LinkedIn URLs.

**Wordmark**
The header uses your real logo: `images/wstnghs-logo-white.png` (transparent background, white strokes — for the dark header). The black version, `images/wstnghs-logo-black.png`, is set as the browser tab favicon. Swap either file to update your branding, or search for `wordmark` in `index.html` to change how it's used.

**Colors and type**
Everything is driven by CSS custom properties at the top of `css/style.css` under `:root`. Change `--brass`, `--safelight`, `--bg`, etc. and the whole site updates.

## Adding a store later

Not built in for now, per your call. When you're ready, the cleanest low-effort path is linking out to Gumroad, Shopify, or Stripe Payment Links from a new nav item or a dedicated section — no need to rebuild the site around it.

## Local preview

No build step required. Just open `index.html` in a browser, or for a local server:

```
npx serve .
```
