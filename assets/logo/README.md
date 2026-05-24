# Grindly Agency, Logo Master Kit

Reconstructed from `Grindly_Agency_logo_4K.png` on May 24, 2026.

## What's in this folder

### Master vector files (SVG)
- `grindly-logo-espresso.svg` , logo in espresso (#20191A) on transparent background. Use on light backgrounds.
- `grindly-logo-porcelain.svg` , logo in porcelain (#FEFEFE) on transparent background. Use on dark backgrounds.
- `grindly-logo-monochrome-black.svg` , pure black version. Use for print, fax, single-color reproduction.

**SVG is the default choice for every digital use case**. Scales to any size with no quality loss, weighs ~14 KB.

### Raster files (PNG with transparency)
For platforms that do not accept SVG (some CMS, Canva uploads, Word, email signatures depending on client).

| File | Resolution | Typical use |
|---|---|---|
| `grindly-logo-espresso-256.png` | 256px wide | Email signature, small thumbnails |
| `grindly-logo-espresso-512.png` | 512px wide | Site nav, deck title slides |
| `grindly-logo-espresso-1024.png` | 1024px wide | Hero sections, print A4 at 96 DPI |
| `grindly-logo-espresso.png` | 882x428 (native) | Source master, archive |

Same set exists for `porcelain` and `monochrome-black`.

### Favicon
- `favicon.ico` , multi-resolution ICO (16, 32, 48, 64, 128). Drop into website root.
- `favicon-16.png`, `-32.png`, `-64.png`, `-128.png` , individual sizes for manifest, Apple touch icon, etc.

The favicon uses the **letter G** in porcelain on espresso background. Reason: the full logo is too horizontal to read inside a 16x16 browser tab. The G is the most recognizable element of the wordmark and stays legible down to 16 px.

### QA sheets (not for production use)
- `_QA-sheet.png` , all 4 variants on the brand colors.
- `_QA-small-sizes.png` , logo legibility at 32, 64, 128 px height.
- `_QA-favicon.png` , favicon legibility at 16, 32, 64, 128 px.

## When to use which variant

| Context | Variant |
|---|---|
| White or ivory backgrounds (most documents, site light sections) | Espresso |
| Dark backgrounds (espresso hero sections, dark mode, video overlays) | Porcelain |
| Single-color print, embossing, watermark on photo | Monochrome black |
| Browser tab, PWA icon, app store | Favicon (picto only) |

## Where to place these files

Recommended GitHub structure:
```
grindlyagency/grindly-tools/
  assets/
    logo/
      grindly-logo-espresso.svg
      grindly-logo-porcelain.svg
      grindly-logo-monochrome-black.svg
      [all PNG variants]
      favicon.ico
      README.md
```

Then reference from any page:
```html
<link rel="icon" href="/assets/logo/favicon.ico">
<img src="/assets/logo/grindly-logo-porcelain.svg" alt="Grindly Agency">
```

## Color reference
- Espresso, `#20191A`
- Porcelain, `#FEFEFE`
- Ivory (background, not for logo), `#F5F0E8`

## Known limits

This logo was **vectorized** from a flat JPEG source, not reconstructed from a designer file. The shapes are faithful but not editable letter-by-letter the way a native Illustrator file would be. For the next stage of Grindly (post 2-3 clients signed, freelance designer hired), commission a native vector reconstruction from the freelance designer to get fully editable masters.

For all current uses (site, deck, invoices, signatures, Canva, social), this kit is production-ready.

## Technical specs
- SVG viewBox: `0 0 1558 658` , aspect ratio ~2.37:1
- PNG masters: 882x428 px, RGBA
- Trace pipeline: PIL alpha extraction → 4x upscale LANCZOS → binary threshold → potrace with `--opttolerance 0.2 --alphamax 1.0 --turdsize 8`
