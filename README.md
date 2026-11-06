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
- `js/stack-reveal.js` — the scroll-stack reveal.
- `js/figures/*.js` — the four illustrations.
- `js/hairline-kernel.js` — the drawing engine the illustrations run on.

Each illustration panel is 4:3. The drawing inside keeps its own 5:4 frame and is zoomed and centred with three
custom properties on its stage: `--z` (zoom), and `--fx` / `--fy` (the point of the 400 × 320 drawing to centre).
They were measured from each drawing's full extent through its loop, so nothing is clipped; raise `--z` to crop tighter.
The pointer still lines up with the drawing at any size.

## Scroll-stack reveal

On wide screens the four cards sit in a deck pinned to the window. Scrolling slides the front card up and away, tipping back, while the cards behind move forward one place; the last card stays and the page scrolls on. It's the stack-scroll reveal from the Framer *Stack Scroll Reveal* project, rebuilt in `js/stack-reveal.js` with the same cards and illustrations.

It turns itself off, leaving the stacked list, on screens under 881px wide, when the tallest card doesn't fit the window, and for visitors who ask for reduced motion. Tabbing to a link in a card behind the front one scrolls that card to the front. The pace and look are constants at the top of the file (`STEP`, `SHRINK`, `PEEK`, `TILT`).

## Styling

Matches the **Case Study Card** component in the Framer project *Case Study Component*: white cards with a 28px radius on a light grey page, a white illustration panel and a red pill button. Colours are custom properties at the top of the `<style>` block in `index.html`.

Type and colour tokens match `hero-hero-existing` and `learning-learning-existing`: **Eudoxus Sans Medium** for headings, labels and the button, **Helvetica** for body copy, with #333 titles, rgb(80,80,80) body and #666 secondary text. Eudoxus is licensed, so it loads from simonalcock.ie rather than living in this repo. Browsers only allow that if simonalcock.ie sends an `Access-Control-Allow-Origin` header for its font files; without it, the text falls back to Helvetica.

## Credits

The illustrations are drawn on the engine of [`@lucasmarkes/hairline`](https://github.com/lucasmarkes/hairline) by Lucas Marques, used under the MIT License — see `js/HAIRLINE-LICENSE.txt`.

The Bohemian FC crest and wordmark belong to Bohemian Football Club.
