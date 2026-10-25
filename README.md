# 📸 Smudge Booth

A free, sketchbook-style online photobooth. Take four photos, style your strip, watch it print out of a little printer, then download it, share it, or print it on paper.

**Live demo:** https://YOUR-USERNAME.github.io/smudge-booth/

<!-- Add a screenshot or GIF here: ![Smudge Booth](assets/preview.png) -->

## Features

- **Real photostrip:** 4 photos stacked into one tall strip with a title and date, saved as a high-resolution PNG.
- **Printing animation:** the strip comes out of a printer slot in jerky steps, with optional printer sounds.
- **Filters:** Natural, Black & white, Sepia, Faded film, Vivid and Pencil sketch. You can change the filter after shooting.
- **Backgrounds:** 9 options, including plain colors and patterns (dots, hearts, stripes, graph paper).
- **Captions and emojis:** a caption under every photo, an editable strip title, and emoji stickers you can stamp anywhere on the strip.
- **Optional pose dares:** turn on random silly prompts for each shot. Off by default.
- **Works on every device:** phones, tablets and desktops, with a front/back camera flip on touch devices.
- **Save your way:** download the PNG, share it to Photos or any app (where the browser supports it), or print two copies per sheet.
- **Private:** everything runs in your browser. No photos are uploaded anywhere.

## How it works

It is a single static `index.html` file with no build step and no dependencies.

- Camera: `getUserMedia`
- Filters, strip layout and export: HTML Canvas, with the pencil-sketch filter written from scratch (grayscale, inverted blur, color dodge)
- Printing sounds: Web Audio API
- Sharing: Web Share API (only shown where supported)
- Fonts: Caveat Brush and Patrick Hand from Google Fonts (SIL Open Font License)

## Run it locally

Browsers only allow camera access on `https` or `localhost`, so do not open the file by double-clicking it. Serve it instead:

```bash
git clone https://github.com/YOUR-USERNAME/smudge-booth.git
cd smudge-booth
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Deploy to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. After a minute your site is live at `https://YOUR-USERNAME.github.io/smudge-booth/`.

GitHub Pages is served over `https`, so the camera works.

## Customize

Everything is in `index.html`. Look for these lists near the top of the script:

| What | Variable |
| --- | --- |
| Pose dares | `DARES` |
| Filters | `FILTERS` and `applyFilter()` |
| Backgrounds and patterns | `BGS` and `pattern()` |
| Emoji palette | `EMOJIS` |
| Strip size and number of photos | `N`, `W`, `PWd`, `PHd` |

## Browser support

Latest Chrome, Edge, Safari (iOS 14.5+) and Firefox. Camera access needs `https` or `localhost`. If the camera is blocked inside an embedded preview, open the page in its own tab.

## Roadmap

- [ ] Drag and resize emoji stickers
- [ ] More dare packs
- [ ] Choose 2, 3 or 4 photos per strip
- [ ] Upload photos instead of using the camera
- [ ] Installable PWA

## Contributing

Issues and pull requests are welcome. Please keep it dependency-free.

## License

[MIT](LICENSE) © 2026 ISHITA SHAH
