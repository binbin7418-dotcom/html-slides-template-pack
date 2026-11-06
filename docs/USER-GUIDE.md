# User Guide — HTML Slide Template Pack

Three presentation templates that run entirely in the browser. No build step, no server, no account — open the file and present.

**English edition (primary) + Chinese edition included.** Every style ships in two languages:

```
templates/minimal-business/   en/  zh/
templates/editorial-magazine/ en/  zh/
templates/dark-tech/          en/  zh/
```

Each language folder is self-contained: an `index.html` plus a `vendor/` folder. Keep them together — the HTML loads its engine (reveal.js) from `vendor/` next to it.

---

## 1. Presenting

1. Double-click `index.html` in any modern browser (Chrome, Edge, Firefox, Safari). It works offline.
2. Navigate with the **arrow keys**, **Space**, or by clicking the on-screen arrows. Press `Esc` for a slide overview, `F` for fullscreen.
3. The deck is designed on a 1440 × 900 (16:9) canvas and scales automatically to your window or projector.
4. Jump straight to a slide by adding `#/3` (0-based) to the address, e.g. `index.html#/5` opens slide 6.

Every deck has the same 10 slide types, in this order:

| # | Slide type | Good for |
|---|------------|----------|
| 1 | Cover | Title, subtitle, presenter / date |
| 2 | Agenda / Contents | What the talk or issue covers |
| 3 | Section divider | Starting a new part |
| 4 | Content — single column | One argument, told in full |
| 5 | Content — two columns | Two related points side by side |
| 6 | Data / chart | KPIs plus one hand-built chart |
| 7 | Table | Scorecards, benchmarks, accounts |
| 8 | Quote | A customer line or a pull-quote moment |
| 9 | Comparison | Before/after, old vs. new |
| 10 | Closing | Thank-you, contact, next step |

Duplicate any `<section>…</section>` block in `index.html` to add more slides of that type, or delete blocks you don't need. Update the small page numbers in each footer (`04 / 10`) to match your final count.

## 2. Changing the text

Open `index.html` in any text editor (VS Code, Notepad, TextEdit). The sample copy is written as realistic filler on purpose: every sentence sits exactly where your sentence should go, so you can see how much text each layout comfortably holds.

- Search for the words you see on the slide and replace them.
- Keep roughly the same length. Headlines are sized for the sample's word count; a much longer headline will wrap to an extra line.
- Numbers in charts are drawn as SVG shapes with text labels — change the label text, and adjust bar heights / line points proportionally. Each chart carries an HTML comment (in the Chinese edition) or is straightforward to read: bar values are commented in the markup of the Minimal Business chart.

## 3. Changing the colours

Each deck defines its palette once, at the top of the `<style>` block, as CSS variables. Change a variable and the whole deck follows.

**Minimal Business** (`--accent` is the only colour — keep it that way for the look to work):

```css
--paper:#FBFBF9;  --ink:#1B1E21;  --accent:#0E5E52;
```

**Editorial Magazine** (brick red is the single accent):

```css
--cream:#F4EEE0;  --ink:#17150F;  --red:#AE3A2C;
```

**Dark Tech** (mint glow on near-black):

```css
--bg:#0A0D12;  --panel:#10151D;  --cy:#3EE6C4;
```

Fonts are system fonts only — nothing to download. Latin text uses Noto Sans / Noto Serif (free, SIL OFL) with Helvetica/Georgia fallbacks; Chinese text uses Noto Sans CJK / Noto Serif CJK with PingFang / Songti fallbacks. If your machine lacks Noto, install it free from Google Fonts for the closest match to the previews.

## 4. Adding images

The templates are type-led and ship without photos, but image slots are easy to add:

- Paste an `<img src="your-image.jpg">` where you want it and keep the file next to `index.html` (or in a subfolder, e.g. `img/`).
- For a full-bleed background on one slide, add `data-background-image="your-image.jpg"` to that slide's `<section>` tag — reveal.js handles the fitting.
- Prefer images at least 1440 px wide so they stay sharp on the 1440 × 900 canvas.

## 5. Exporting to PDF

Print styles are included and tested — each slide becomes exactly one PDF page, colours included.

1. Open the deck with `?print-pdf` added to the address: `index.html?print-pdf`
2. Wait a second for the pages to stack, then print with `Ctrl/Cmd + P`.
3. Choose **Save as PDF**, set margins to **None**, and tick **Background graphics** (required, or the Dark Tech deck will print without its dark background).
4. Save. You will get a 10-page PDF (or however many slides your edited deck has), one slide per page, in order.

Tip: in Chrome, the print preview should show each slide filling its page edge to edge. If a page looks split, reload the `?print-pdf` view and print again — the layout needs its one second to settle.

## 6. Licence

**You may**

- Use these templates for your own presentations — personal, internal, client-facing, commercial — in person, on video calls, recorded, or exported to PDF/images.
- Modify the templates (text, colours, layouts) for your own use.

**You may not**

- Resell, redistribute, sublicense, or share the template files themselves (modified or not) — including uploading them to template marketplaces, file-sharing sites, or public repositories.
- Claim the template designs as your own product.

One purchase covers one person / one business entity. The underlying reveal.js engine is MIT-licensed (see `vendor/LICENSE` in each folder) and is not restricted by the terms above.

Sample content in the decks is fictional and written for layout purposes — companies, people, magazines and figures are invented. Replace them with your own before presenting.

## 7. Troubleshooting

- **Slides look unstyled / stacked as plain text** — the `vendor/` folder was moved or renamed. It must sit next to `index.html`.
- **A headline overflows its slide** — shorten it. The layouts are tuned to the sample lengths.
- **PDF pages come out white for Dark Tech** — enable **Background graphics** in the print dialog (step 5.3).
- **Fonts look different from the previews** — install Noto Sans / Noto Serif (and the CJK variants for the Chinese edition); fallbacks work but metrics differ slightly.
