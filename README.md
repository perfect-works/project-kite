# Project Kite: Kite Thrust Model V2

Interactive model of towing-kite thrust for the Hanwha MT-50 MR tanker on the Houston ⇄ Rotterdam route (Texas A&M OCEN 407 capstone).

**Open the page:** see the GitHub Pages link in this repo's About panel, or open `index.html` in any browser.

## What it does

- Circle-centre version of the Traut et al. (2014) kite model: `T = K·Va²·cos³ε·cos³(δ/2)`, with `K = ½ρA·√(CL² + CD²)·(1 + CL²/CD²)` (Loyd 1980).
- Wind: ERA5 monthly means at six route waypoints (team sheet "Route1 Houston to Rotterdam", Sep 2025 – Aug 2026), corrected to kite height with a power law (α = 0.11), with the scatter within each month modelled as a Rice distribution.
- Sliders for kite area, tether length, tether elevation, L/D and tether limit; month and route-position controls; full derivation on the page.

## Deployment tab

Second tab on the same page: the bending moment at the base of the existing foremast while the kite is hoisted on it and filling, before release. Drag the kite up or down the mast to change its height. Wind comes from the same month / position / leg controls (ERA5 monthly mean, shear-corrected to the kite's height, plus the ship's headwind); kite area from the shared area bar. Side force = 1.16 gust × ½ρA·C_R·V_a² (whole canopy force sideways while it fills), moment = side force × height. Mast heights are measured from the GA drawing (fo'c'sle deck 22.5 m above baseline, mast top 8.7 m above the deck). Open it directly with `index.html#deployment`; its constants are in the `DEPLOY` block in the script.

## Changing the model

Everything is in `index.html`. The `CONFIG` block at the top of the script holds every fixed parameter; the `SLIDERS` block under it sets slider ranges and which start locked. Edit, save, reload.

## Known limitations

No tether weight or drag (a longer tether only ever helps), no kite mass, no gust loads, leeway or rudder drag, and the same main-engine power is used for laden and ballast legs. The monthly wind scatter is an assumption; rerun with hourly ERA5 before quoting numbers in the report.
