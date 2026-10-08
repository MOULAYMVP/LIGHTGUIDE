# LightBurn Installation Guide — lightos.site

A single self-contained page. No build step, no dependencies, no framework.

```
index.html   the whole site
```

## Deploy to Cloudflare Pages

**Direct upload**

1. Cloudflare dashboard → Workers & Pages → Create → Pages → Upload assets
2. Drag this folder in
3. Custom domains → add `lightos.site`

**From this repository**

1. Pages → Create → Connect to Git → pick `LIGHTGUIDE`
2. Framework preset: **None**
3. Build command: *leave empty*
4. Build output directory: `/`
5. Custom domains → add `lightos.site`

## Preview locally

```bash
python3 -m http.server 4321
```

Then open http://localhost:4321

## Adding videos

Near the bottom of `index.html`:

```js
var VIDEOS = [
  { id: "YOUTUBE_ID", title: "Getting started with LightBurn" },
];
```

Each entry renders as an embedded player. While the list is empty the page
links to the vendor's YouTube channel instead, so it never shows a broken
player.

## Languages

English, German and French are all in `index.html`, switched client-side.
The choice is remembered, and the page defaults to the visitor's browser
language. To edit copy, find the matching `data-lang="en|de|fr"` block.
