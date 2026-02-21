# FoF Deluxe Tracker — v2.0 Update

Major update to the Fields of Fire Deluxe Tracker. This version adds full support for all four campaigns and overhauls the UI and data accuracy.

---

## New: Multi-Campaign Support

The tracker now covers **all 31 missions across 4 campaigns**:

- **Normandy** (WWII) — 7 missions (existing, refined)
- **Naktong River** (Korea, 1950) — 7 missions *(new)*
- **Heartbreak Ridge** (Korea, 1951) — 8 missions *(new)*
- **Vietnam** (1966–1968) — 9 missions including M7A/M7B split *(new)*

Select a campaign from the new dropdown, pick your mission, and click **New Mission (Campaign)** — everything auto-fills.

### What auto-populates per mission:
- Mission type, duration, visibility, map dimensions
- Enemy tactics and experience
- US and Enemy grenade VOF modifiers
- Battalion Fire Mission availability
- All fire support agencies with correct draw numbers per column
- HQ experience levels (campaign-specific TO&E)
- Unit ammo allocations (campaign-specific TO&E)
- Attachments (Arty FO, Mtr FO, FAC, Tanks, HMGs, Engineers, RCL teams, etc.)

### Campaign-specific TO&E differences handled:
- **Normandy**: Bazookas, SCR300 radios, .30 cal LMGs
- **Naktong River**: 57mm RCL teams, Runners, 75mm RCL permanent attachments, HMG Platoon, M4 Shermans
- **Heartbreak Ridge**: Mixed experience levels per unit (e.g., 57RCL teams at Vet/Line/Green), 4.2" Regimental Mortar Company, Divisional Artillery (105mm + 155mm)
- **Vietnam**: PRC25 radios, M60 MG teams, 60mm mortar team, 4.2" mortar platoon, FAC/O-2 Airborne FAC, M48 Patton tanks, AC-47 Gunship, Attack Helicopters, FPF support

---

## New: Dynamic Fire Missions Tab

The Fire Missions tab now dynamically adjusts its columns based on the selected mission:

- **Normandy**: 3 draw columns (Arty FO, Mtr FO, CO HQ)
- **Naktong/Heartbreak/Vietnam**: Up to 5–6 draw columns (FAC, Arty FO, Mtr FO, CO HQ, PLT HQ) — only columns present in that mission's FS table are shown

All 193 fire mission entries across 31 missions were verified cell-by-cell against the mission books (~970 individual draw values).

---

## UI Improvements

- **Campaign + Mission dropdowns** — mission list auto-updates when you switch campaigns
- **New Mission buttons moved to top** of the Setup tab and made larger for easier access
- **Weapons tab removed** — redundant with unit tracking
- **Fire Missions tab added** — dedicated tab for fire support tracking with draw columns
- **HQ blocks simplified** — cleaner layout with auto-calculated command modifier (Green=–1, Line=0, Veteran=+1)
- **Ammo columns** refined to show only for discrete heavy weapons (mortars, MGs, AT weapons, RCLs, tanks)

---

## Bug Fixes

- HQ experience no longer defaults to "Line" — now correctly pulls mission-specific values
- Fire mission draw data stored as separate fields (Arty FO Draw, Mtr FO Draw, CO HQ Draw, FAC Draw, PLT HQ Draw) instead of concatenated string
- Ammo tracking scoped to heavy weapons only (no more ammo columns on rifle squads)
- Save/load compatibility preserved across all changes

---

## Data Accuracy

Every mission's data was extracted directly from the official FoF Deluxe mission books and audited:
- Setup parameters (type, duration, visibility, map, tactics, enemy experience)
- Fire support tables (agency, ammo type, combat modifier, all draw columns, mission count)
- HQ experience levels per campaign TO&E
- Unit ammo allocations per campaign TO&E
- Attachment lists per mission
- Grenade VOF modifiers per campaign (US –4 across all; Enemy –4 Normandy, –3 Korea/Vietnam)

---

*This is an unofficial fan-made play aid. Fields of Fire is designed by Ben Hull and published by GMT Games.*
