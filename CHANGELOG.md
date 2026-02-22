# FoF Deluxe Tracker — Changelog

All notable changes to this project are documented here. Newest version first.

---

## v3.0 — 2025-02-22

### NCM Calculator — Rebuilt & Verified

The NCM calculator has been corrected and verified against the Charts & Tables Player Aid 1 (Infantry Combat Modifiers) and rulebook §6.4–§6.5. Thanks to Colin Parsons for flagging the errors in v2.0.

#### VOF Modifiers
- **Fixed:** VOF types now use dropdown selectors with correct values instead of uniform checkboxes
- **Fixed:** Removed Flame (F!) and Demo (D!) from VOF selection — these resolve outside NCM per §6.5.2 and §6.5.3. A successful Demo kills all occupants; a successful Flame is an automatic hit. Neither uses the NCM table.
- **Fixed:** Incoming! and Air Strike! changed from preset dropdowns to free-entry fields — the Player Aid lists both as "Varies," so the tracker now lets you enter whatever NCM value your mission specifies
- **Fixed:** Grenade (G!) correctly offers –3 or –4
- **Verified** all fixed VOF values against the Player Aid: S = 0, A = –1, H = –3, G! = –3/–4, S! = –3, Mines! = –4

#### Combat Modifiers (Step 3)
- Crossfire → –1, Concentrated Fire → –1, Grenade Miss → –1, Demo Miss → –2, Exposed → –2, Pinned → +2 — all verified against Player Aid
- Demo Miss (–2) remains as a checkbox, which is the correct mechanism for a failed Demo throw (§6.5.2)

> Every value in the NCM calculator is now either verified to the Charts & Tables Player Aid or explicitly deferred to mission instructions. No assumptions.

---

## v2.0 — 2025-02-15

### Multi-Campaign Support

The tracker now covers **all 31 missions across 4 campaigns**:
- **Normandy** (WWII) — 7 missions (existing, refined)
- **Naktong River** (Korea, 1950) — 7 missions
- **Heartbreak Ridge** (Korea, 1951) — 8 missions
- **Vietnam** (1966–1968) — 9 missions including M7A/M7B split

Select a campaign, pick your mission, click **New Mission (Campaign)** — everything auto-fills.

#### Auto-populated per mission:
- Mission type, duration, visibility, map dimensions
- Enemy tactics and experience
- US and Enemy grenade VOF modifiers
- Battalion Fire Mission availability
- All fire support agencies with correct draw numbers per column
- HQ experience levels (campaign-specific TO&E)
- Unit ammo allocations (campaign-specific TO&E)
- Attachments (Arty FO, Mtr FO, FAC, Tanks, HMGs, Engineers, RCL teams, etc.)

#### Campaign-specific TO&E:
- **Normandy**: Bazookas, SCR300 radios, .30 cal LMGs
- **Naktong River**: 57mm RCL teams, Runners, 75mm RCL permanent attachments, HMG Platoon, M4 Shermans
- **Heartbreak Ridge**: Mixed experience levels per unit, 4.2" Regimental Mortar Company, Divisional Artillery (105mm + 155mm)
- **Vietnam**: PRC25 radios, M60 MG teams, 60mm mortar team, 4.2" mortar platoon, FAC/O-2 Airborne FAC, M48 Patton tanks, AC-47 Gunship, Attack Helicopters, FPF support

### Dynamic Fire Missions Tab

Fire Missions tab dynamically adjusts columns based on the selected mission:
- **Normandy**: 3 draw columns (Arty FO, Mtr FO, CO HQ)
- **Naktong/Heartbreak/Vietnam**: Up to 5–6 draw columns (FAC, Arty FO, Mtr FO, CO HQ, PLT HQ)

All 193 fire mission entries across 31 missions verified cell-by-cell (~970 individual draw values).

### UI Improvements
- Campaign + Mission dropdowns with auto-updating mission list
- New Mission buttons moved to top of Setup tab
- Weapons tab removed (redundant)
- Fire Missions tab added
- HQ blocks simplified with auto-calculated command modifier
- Ammo columns scoped to heavy weapons only

### Bug Fixes
- HQ experience now correctly pulls mission-specific values
- Fire mission draw data stored as separate fields
- Save/load compatibility preserved

### Data Accuracy
Every mission's data extracted directly from the official FoF Deluxe mission books and audited:
- Setup parameters, fire support tables, HQ experience levels, unit ammo allocations, attachment lists
- Grenade VOF modifiers per campaign (US –4 all campaigns; Enemy –4 Normandy, –3 Korea/Vietnam) — now correctly reflected in the NCM calculator as of v3.0

---

## v1.0 — 2025-02-08

Initial release. Normandy campaign support, turn sequence walkthrough, unit roster, command tracker, NCM calculator, enemy tracker, weapons & ammo tracking, comms & assets, map grid, battle journal, campaign log. Single HTML file, offline capable.

---

*This is an unofficial fan-made play aid. Fields of Fire is designed by Ben Hull and published by GMT Games.*
