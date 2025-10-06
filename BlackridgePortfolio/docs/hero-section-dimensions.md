# Hero Section Dimensions

This reference captures the live spacing rules that define the hero area so you can prepare a background or hero asset that aligns exactly with the current layout.

## Section Canvas
- **Full width:** the `<section>` spans the viewport (`width: 100%`), so any section-wide background image should be prepared for the largest target viewport and use `background-size: cover` when applied.
- **Horizontal padding:** the `.section-crestone` utility applies `padding-left` and `padding-right` of `1.5rem` (24px). The inner Tailwind `container` clamps the content column to `max-width: 80rem` (1280px) while keeping the 24px side padding until the viewport is wider than 1536px.
- **Vertical padding:** Tailwind utilities overwrite the base spacing, resulting in `padding-top: 8rem` (128px) and `padding-bottom: 6rem` (96px). When combined with the hero visual height below, this gives you the total vertical canvas.

## Hero Visual Frame (`#hero-visual`)
The media well that renders the hero artwork uses `height: clamp(340px, 55vw, 580px)`. That translates into the following heights at key breakpoints:

| Viewport width | Computed 55vw | Applied height | Section height (visual height + padding) |
| -------------- | ------------- | -------------- | ---------------------------------------- |
| 480px          | 264px         | 340px (min)    | 340 + 128 + 96 = **564px**               |
| 768px          | 422px         | 422px          | 422 + 128 + 96 = **646px**               |
| 1024px         | 563px         | 563px          | 563 + 128 + 96 = **787px**               |
| 1280px         | 704px         | 580px (max)    | 580 + 128 + 96 = **804px**               |
| 1440px         | 792px         | 580px (max)    | 580 + 128 + 96 = **804px**               |
| 1920px         | 1056px        | 580px (max)    | 580 + 128 + 96 = **804px**               |

Use the “Applied height” column when preparing raster assets for the hero visual, and the “Section height” column when you want an image to cover the entire hero section background.

## Practical Export Guidance
- **Recommended export size for full-bleed section artwork:** 1920 × 804px. This covers widescreen desktops while remaining aligned with the section’s effective height.
- **Safe area for focal content:** keep essential details within a 1280 × 580px box centered horizontally so they remain visible on laptops down to 1280px wide.
- **Color matching:** the runtime script samples the hero image’s average tone and syncs the section background (`--hero-image-black`) to that value, so any exported background will blend seamlessly.

Re-exporting an updated image with these measurements ensures it will cover the hero section precisely without stretching or cropping issues across breakpoints.
