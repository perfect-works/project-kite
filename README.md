# Project Kite: Kite Thrust Model V2

Interactive model of towing-kite thrust for the Hanwha MT-50 MR tanker on the Houston ⇄ Rotterdam route (Texas A&M OCEN 407 capstone).

**Open the page:** see the GitHub Pages link in this repo's About panel, or open `index.html` in any browser.

## What it does

- Circle-centre version of the Traut et al. (2014) kite model: `T = K·Va²·cos³ε·cos³(δ/2)`, with `K = ½ρA·√(CL² + CD²)·(1 + CL²/CD²)` (Loyd 1980).
- Wind: ERA5 monthly means at six route waypoints (team sheet "Route1 Houston to Rotterdam", Sep 2025 – Aug 2026), corrected to kite height with a power law (α = 0.11), with the scatter within each month modelled as a Rice distribution.
- Sliders for kite area, tether length, tether elevation, L/D and tether limit; month and route-position controls; full derivation on the page.

## Changing the model

Everything is in `index.html`. The `CONFIG` block at the top of the script holds every fixed parameter; the `SLIDERS` block under it sets slider ranges and which start locked. Edit, save, reload.

## Known limitations

No tether weight or drag (a longer tether only ever helps), no kite mass, no gust loads, leeway or rudder drag, and the same main-engine power is used for laden and ballast legs. The monthly wind scatter is an assumption; rerun with hourly ERA5 before quoting numbers in the report.
