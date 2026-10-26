# Dot studio

A small web app for making random dot images. Set the canvas size, the dot diameter, how many dots (either a count or a percentage coverage of the image), the dot color and opacity, and a background color or transparency. Then download the result as a full-resolution PNG.

**Live app:** https://kefangpsych.github.io/random-dot-generator/

## How it works

- Each dot's center is drawn independently and uniformly from the canvas pixels, so dots can overlap and dots at the edges are cropped.
- **Coverage** is the dots' total area as a share of the image, ignoring overlaps: `count × π(d/2)² / (width × height)`. Because dots overlap at random, the share of the image actually covered is on average about `1 − e^(−coverage)`; the app shows this estimate.
- The **seed** makes patterns repeatable: the same settings and seed always give the same image.
- All settings are kept in the page URL, so **Copy link** shares the exact pattern.

Everything runs in the browser in a single `index.html` with no dependencies, and it works offline.
