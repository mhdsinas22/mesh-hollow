# Mapleash Resort · Virtual Tour

A 3D virtual tour website for Mapleash Resort, Wayanad, Kerala, built with three.js (r128).
Scrolling walks the camera through the resort: arrival courtyard and reception pavilion, the
infinity pool and kids' area, the cottages, and a plan-your-visit stop. Guests can step inside
a cottage room (four-poster bed, in-room jacuzzi, forest window) and look around.
Each stop links to a real photo of the resort. A Daytime/Evening switch relights the scene.

## Editing resort details

Open `index.html` and edit the `RESORT` object near the top of the script:
`phone`, `whatsapp` and `email` rows appear on the Visit stop as soon as they are filled in.
Photos live in `images/`.

## Run locally

```bash
python3 -m http.server 8000
```

## Deploy

Served by GitHub Pages from the `gh-pages` branch. Push changes with:

```bash
git push origin main main:gh-pages
```

## Rendering and assets

- Realistic lighting uses image-based lighting from CC0 HDRIs by Poly Haven (via the `@pmndrs/assets` package): `images/env/park.exr`, `sunset.exr`, `apartment.exr`.
- `vendor/EXRLoader.js` and `vendor/fflate.min.js` come from three.js r128 (MIT).
- The room's window view (`images/view.jpg`) is cropped from the resort's own pool photo.
- Materials (wood, plaster, linen, paving, pool mosaic, water ripples) are generated in the browser.

Test locally through a web server (the HDRIs do not load from `file://`).
