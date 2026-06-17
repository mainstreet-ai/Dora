# Dora Fennell Wreaths — Website

A single-page site to showcase Dora's handmade wreaths and collect order requests, ready to host for free on GitHub Pages.

## Files
```
dora-wreaths/
├── index.html
└── images/
    ├── halloween-noir.jpg
    ├── patriotic-meadow.jpg
    ├── autumn-harvest.jpg
    ├── let-freedom-ring.jpg
    ├── winter-snowman.jpg
    └── blush-autumn.jpg
```

## Before you publish — 2 things to fix

### 1. Connect the request form (required)
The contact form needs somewhere to send submissions to, since this is a static site with no backend. The easiest free option is **Formspree**:

1. Go to https://formspree.io and sign up free (50 submissions/month free, no credit card).
2. Create a new form, and copy the unique endpoint it gives you — it looks like `https://formspree.io/f/abc12345`.
3. Open `index.html`, find this line (search for `REPLACE_WITH_YOUR_FORM_ID`):
   ```html
   <form method="POST" action="https://formspree.io/f/REPLACE_WITH_YOUR_FORM_ID">
   ```
4. Replace `REPLACE_WITH_YOUR_FORM_ID` with the ID Formspree gave you.
5. Formspree will send an email to your inbox every time someone submits the form. You confirm your email the first time you set it up.

This uses a standard HTML form POST (not JavaScript), so there are no CORS issues — it'll just work once the endpoint is in place.

### 2. Add the real Facebook link (required)
Search `index.html` for `href="#" target="_blank"` (there are two — one in the request section, one in the footer) and replace `#` with Dora's actual Facebook page URL, e.g.:
```html
<a href="https://www.facebook.com/yourpagename" target="_blank" rel="noopener">
```

## Publishing to GitHub Pages

1. Create a new repository on GitHub (e.g. `dora-wreaths`).
2. Upload `index.html` and the `images` folder, keeping that same folder structure.
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment," set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`.
5. Save. GitHub will give you a live URL like `https://yourusername.github.io/dora-wreaths/` within a minute or two.

That URL is what you share — on Facebook, in a bio link, anywhere.

## Customizing later
- **Add more wreaths:** duplicate one `<article class="wreath-card">` block in the gallery section, swap the image filename, alt text, title, description, and season tag.
- **Swap the hero photo:** change the `src` on the `<img>` inside `<section class="hero">`.
- **Future e-commerce:** when ready, services like Shopify Lite, Square, or even a simple "Buy Now" PayPal button can slot into the wreath cards without rebuilding the site.
