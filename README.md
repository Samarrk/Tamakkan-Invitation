# Tamakkan Booth Invitation

A single-file invitation site for our booth at the Career and Innovation Forum 2026 (Umm Al-Qura University).

**Stack:** plain HTML + CSS + tiny JS. No build step, no framework.

**Booth:** AI-F-3 · Tuesday, June 9, 2026 · 11:30 AM – 1:00 PM · King Abdulaziz Hall

## Files
- `index.html` — the whole site
- `logo.png` — the Tamakkan logo

## Deploy to GitHub Pages (~2 minutes)

1. Create a new public repo on GitHub, e.g. `tamakkan-invitation`.
2. Drop both files (`index.html` and `logo.png`) at the repo root.
3. Push to the `main` branch.
4. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
5. Wait ~30 seconds. Your site goes live at:
   ```
   https://<your-username>.github.io/tamakkan-invitation/
   ```

If you want a quick preview locally first, just open `index.html` in any browser — the site is fully static.

## Customizing

Everything is in one file. Common tweaks:

- **Description text** → search for `يسرّنا فريق` inside `<p class="description">`
- **Date/time/location** → search for `الثلاثاء، 9 يونيو 2026` inside the `booth-row` divs
- **Booth number** → search for `AI-F-3`
- **Countdown target** → look for `const target = new Date('2026-06-09T11:30:00+03:00');` in the script section
- **Colors** → the `:root` block at the top of `<style>` holds all the colors as CSS variables (`--teal`, `--teal-bright`, `--bg`, etc.)

## What's in the design

- **Dashcam POV background**: CSS perspective transform + animated dashed lane line. No libraries.
- **HUD overlay**: top bar with REC indicator, live clock, and Tamakkan-OS branding. Bottom bar with speed + Jetson FPS (real numbers from our pipeline).
- **Fake YOLO bounding boxes**: pulsing detection overlays — nods to the actual perception system.
- **Glass card**: backdrop-filter blur with teal/green border, holds the invite content.
- **Countdown**: live ticker to 11:30 AM Saudi time, switches to a "we're live now" message during the booth, and to "thanks for visiting" after.

All animations respect `prefers-reduced-motion` for accessibility.
