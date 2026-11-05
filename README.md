# Simon Alcock — Case Studies

The case studies section for the homepage of the new simonalcock.ie: four stacked cards, each with the case study's copy beside an animated, interactive isometric line illustration. Built with plain HTML, CSS and JavaScript — no build step.

## Use it

Open `index.html` in a browser, or view the GitHub Pages site.

Each illustration plays a short loop on its own, and answers the pointer when you hover it. Loops pause while a card is offscreen, and nothing plays for visitors who ask for reduced motion.

## Content

Copied verbatim from the current simonalcock.ie homepage, in the same order:

| # | Case study | Illustration | Links to |
| --- | --- | --- | --- |
| 1 | Redesigning the Aer Lingus booking flow | `flights` — a flight results page; the fare under the cursor lifts out of its card | [/aer-lingus-booking-flow/](https://simonalcock.ie/aer-lingus-booking-flow/) |
| 2 | How my conversion optimisation projects increased revenue by €57 million | `phone` — three test screens stacked over a control phone, closing into one | [/conversion-designer/](https://simonalcock.ie/conversion-designer/) |
| 3 | Complying with U.S. accessibility legislation | `accessibility` — the accessibility mark on a turntable inside a resizing selection box | [/accessibility-design/](https://simonalcock.ie/accessibility-design/) |
| 4 | Rebuilding Bohemian FC’s web presence | `bohs` — the club crest and wordmark turning from isometric to face-on | [/portfolio/bohemianfc/](https://simonalcock.ie/portfolio/bohemianfc/) |

To edit copy, change the `<article class="case">` blocks in `index.html`. To swap an illustration, change the card's `data-figure` to another figure's name.

## Files

- `index.html` — the section: markup, styles and the copy.
- `js/case-studies.js` — mounts a figure into every `[data-figure]` stage and starts its loop.
- `js/figures/*.js` — the four illustrations.
- `js/hairline-kernel.js` — the drawing engine the illustrations run on.

Each stage keeps the figures' 5:4 frame, centred in its panel, so the pointer lines up with the drawing at any size.

## Styling

Matches the **Case Study Card** component in the Framer project *Case Study Component*: white cards with a 28px radius on a light grey page, a light grey illustration panel and a red pill button. Colours are custom properties at the top of the `<style>` block in `index.html`.

Type is **Plus Jakarta Sans** from Google Fonts, standing in for Eudoxus Sans, which the current site uses. To switch, self-host Eudoxus Sans and change `--font`.

## Credits

The illustrations are drawn on the engine of [`@lucasmarkes/hairline`](https://github.com/lucasmarkes/hairline) by Lucas Marques, used under the MIT License — see `js/HAIRLINE-LICENSE.txt`.

The Bohemian FC crest and wordmark belong to Bohemian Football Club.
