# Fields of Fire Deluxe Tracker

A browser-based mission tracker for **Fields of Fire Deluxe** (GMT Games, 2024) — a solitaire tactical wargame covering WWII, Korea, and Vietnam.

## Features

- **4 Full Campaigns** with auto-populated mission data:
  - **Normandy** (WWII) — 7 missions
  - **Naktong River** (Korea, 1950) — 7 missions
  - **Heartbreak Ridge** (Korea, 1951) — 8 missions
  - **Vietnam** (1966–1968) — 9 missions (31 total)
- **Auto-Fill on Mission Select** — HQ experience, unit ammo, fire support tables, attachments, enemy parameters all populate from mission book data
- **Dynamic Fire Missions Tab** — draw columns adjust per campaign/mission (Arty FO, Mtr FO, CO HQ, PLT HQ, FAC as applicable)
- **Unit Tracking** — status, location, assignment, ammo for all TO&E units
- **HQ Command Tracking** — command markers, experience, modifiers with auto-calculated command bonus
- **Tactical Controls** — LOD, LOA, phase lines, boundaries
- **Save/Load** — full game state persists to browser localStorage

## Usage

1. Open `FoF_Deluxe_Tracker.html` in any modern browser
2. Select a **Campaign** and **Mission** from the dropdowns
3. Click **⟳ New Mission (Campaign)** to auto-populate all mission data
4. Track your game across the Setup, Units, HQ, and Fire Missions tabs

No build step, no dependencies, no server — just one HTML file.

## Requirements

- Modern browser with JavaScript enabled (Chrome, Firefox, Edge, Safari)
- Internet connection on first load (pulls React + Babel from CDN)

## Campaign Data Sources

All mission data was extracted from the official GMT Games Fields of Fire Deluxe mission books and verified cell-by-cell against source material (193 fire mission entries, ~970 individual values).

## Disclaimer

This is an unofficial fan-made play aid. **Fields of Fire** is designed by Ben Hull and published by [GMT Games](https://www.gmtgames.com/). You need a copy of the game to use this tracker.

## License

MIT License — see [LICENSE](LICENSE)
