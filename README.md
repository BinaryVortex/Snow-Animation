# Snow Animation

A lightweight, responsive snowfall animation built with plain HTML, CSS and JavaScript.

![Preview](./Screenshot%202024-08-25%20185210.png)

## Overview

This small project renders a layered snowfall effect on a full-screen canvas. Snowflakes are split into three layers (near, middle, far) to create a parallax/depth illusion. It's intentionally simple and easy to customize.

Built with:
- HTML (index.html)
- CSS (style.css)
- JavaScript (script.js)

## Features

- Three layers of snow for depth (near / middle / far)
- Configurable particle count and properties
- Full-screen, responsive canvas
- Minimal, dependency-free code — drop it into any static site

## Screenshot

The screenshot included in the repository shows the effect. If you're viewing this on GitHub the image above should render from the repository root file `Screenshot 2024-08-25 185210.png`.

## Run / Demo

1. Clone the repo:

   git clone https://github.com/BinaryVortex/Snow-Animation.git
   cd Snow-Animation

2. Open `index.html` in your browser (double-click or `Open File`).

3. Or serve it locally (recommended if browsers block local scripts):

   - Python 3: `python -m http.server 8000`
   - Node (http-server): `npx http-server` or `npm i -g http-server`

Then navigate to http://localhost:8000 and open `index.html`.

## Configuration

Open `script.js` and tweak the values near the top:

- `particleSettings.count` — number of snowflakes per layer (default: 250). Lower to improve performance.
- The `createsnowfall` function constructs particles for each layer using `new Particle(area, alpha, vy)`. These values control size, opacity and vertical speed.

Example: reduce density for better performance on mobile:

```js
particleSettings.count = 120;
```

Or change the speed/size for the "near" layer:

```js
// inside createsnowfall when flag == 'near'
particle = new Particle(5, 0.95, 0.4); // bigger & slightly faster
```

## Suggestions for improvements

- Add wind by modifying horizontal velocity and applying a small per-frame offset to `x`.
- Pause/resume on tab visibility change to save CPU.
- Add a control panel (slider) to let users change snow intensity and color.
- Export as a reusable module/component.

## Contributing

PRs and issues are welcome. If you open a PR, please include a short description of the change and screenshots if applicable.

## License

No license specified. If you'd like this project to be open source, add a LICENSE file (MIT is a common choice).

---

Made by BinaryVortex
