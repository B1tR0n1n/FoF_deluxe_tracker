# Fields of Fire — Deluxe Mission Tracker Changelog

Single-file HTML tracker for Fields of Fire Deluxe (GMT Games, 3rd Edition).
No install. Works in any browser. Auto-saves to local storage.

---

## v3.1.1 — Rules Audit Patch (2025-02-22)

Full cross-reference audit against the 3rd Edition Series Rules and all four campaign books (Normandy, Heartbreak Ridge, Naktong River, Vietnam). Fixes two confirmed rules bugs, adds missing units and HQs for Korea/Vietnam campaigns, and sizes the map grid per mission.

### Rules Fixes

- **Command Cover modifier corrected (§4.1.2A).** Was a leveled dropdown (+1/+2/+3) matching NCM cover levels. Rules say ANY cover marker on a command draw = flat +1, regardless of type. Changed to binary Yes/No. Cover *level* only matters for NCM combat resolution (§6.4), not command draws.

- **Stacking penalty now includes Air Strike! (§5.3).** Was only checking for G! and Incoming! when gating the stacking penalty. Rules say "each unit attacked by a Grenade, Incoming! **or Air Strike!** VOF receives a –1 stacking penalty modifier." Air Strike! added to eligibility check. UI label updated to "G!/Inc!/Air! only."

### Data Fixes — Unit Roster

- **4TH PLT HQ added to HQ_NAMES.** Vietnam TO&E Option 2 includes a 4th Rifle Platoon with its own HQ. Was in UNIT_DEFS but missing from the command tracker — couldn't draw commands. Now gets a full command draw slot and grid.

- **HMG PLT HQ added to HQ_NAMES and UNIT_DEFS.** Naktong M1 attaches a full HMG Platoon with its own HQ (Green exp, SCR536 radio). Was simplified to just "HMG Plt" without command capability. Now trackable as a command element.

- **Runners (1/Runner, 2/Runner) added to UNIT_DEFS.** Naktong TO&E includes permanent Runner units. Were not in the unit roster — couldn't be tracked. Added as ATTACH group.

### Data Fixes — Map Grid

- **Map grid now sizes per mission.** Was hardcoded 6×6 for all missions. Each mission specifies its own row×col dimensions in the data (e.g., Trévières is 3×4, Mole City is 4×8). Card Tracker now generates the correct grid on mission load and displays dimensions in the section title.

### Functional Fixes

- **Delete buttons added to Journal, Campaign Results, Replacements, and FM Log.** Previously you could add rows but not remove them.

- **Autosave comment corrected.** Code comment said "every 5 seconds" — actual interval is 300000ms (5 minutes). Comment now matches the code and the UI label.

### UI

- **Black background with brown input fields.** Every editable field (dropdowns, number inputs, text fields) renders as a warm brown box on the black document background. When a field has a value, the border shifts to gold and the label brightens. Empty/default fields stay dim. This applies uniformly across all 11 tabs — no exceptions.

### Not Changed

- **D!/F! in Command VOF dropdown** — left in place. While Demolition and Flamethrower are one-shot attacks resolved outside normal combat, treating them as –3 VOF for command draws is conservative and harmless. Removing them could surprise a player mid-game.

### Save Compatibility

Full backward compatibility with v3.0 and v3.1 saves. Old cover format (numeric levels) migrates to binary on load.

---

## v3.1 — Rules Accuracy & Command Tracker (2025-02-22)

NCM calculator restructured against the official Player Aid (Infantry Combat Modifiers table). Command Tracker modifiers wired into a live calculation per §4.1.2. Thanks to the BGG community for catching issues.

### NCM Calculator

**All Pinned (+2) now overrides all other VOF.** Was competing in the lowest-value pool — selecting All Pinned alongside Heavy would ignore All Pinned and use –3. Checking All Pinned now disables all other VOF inputs. PA: *"Overrides normal VOF."*

**Grenade (G!) is cumulative.** Replaced the single –3/–4 dropdown with a count input. Enter total G! markers and how many hit at –4. Multiple grenades stack: 2× G! at –3 = –6. PA: *"G! VOF are cumulative with each other."*

**Sniper (–3) moved from Step 1 (VOF) to Step 3 (Other Modifiers).** PA lists Sniper under "Other." Includes reminder that rest of card resolves under S VOF.

**Rocket/Grenade Miss reverted to checkbox (–1, once per card).** Was incorrectly a numeric input allowing multiples based on a community suggestion. PA: *"Apply only once per card."*

**Stacking penalty reworked.** Was a flat –1 checkbox applied to all VOF types. Now numeric (–1 per step over 3 under cover), active only when G! or Incoming! VOF is present. Grayed out otherwise. PA: *"Apply only to G! & Incoming VOF."*

**Exposed (–2) confirmed.** Not on the PA summary card but verified in §6.4 and worked examples.

**Input validation** added: C&C and Cover positive-only, Burst/Inc!/Air! negative-only.

**Critical Hit / Hit Effect reference** added as collapsible panel (§6.4.3–6.4.4, §7.10.3).

**NCM clamped to –4 / +6.** Shows unclamped value when clamping activates.

### Command Tracker

**All §4.1.2 modifiers now auto-compute.** Pin, VOF, and Cover dropdowns existed in v3.0 but did not feed into the Total — they were cosmetic. Now wired:

| Condition | Modifier | Rule |
|-----------|----------|------|
| Green | –1 | §4.1.2A |
| Veteran | +1 | §4.1.2A |
| Pinned | –1 | §4.1.2A |
| Under Cover | +1 / +2 / +3 | §4.1.2A |
| Small Arms VOF | –1 | §4.1.2B |
| Automatic Weapons VOF | –2 | §4.1.2B |
| H / S! / G! / Inc! / Air! VOF | –3 | §4.1.2B |
| No Contact | +1 (auto) | §4.1.2C |

**Cover dropdown** with levels: None, +1 Basic/Foxhole, +2 Trench, +3 Bunker/Pillbox.

**Command minimums enforced:** Activation min 1 (§3.3.1), Initiative min 0 (§3.3.2), CO Staff fixed 1 (§3.3.2c), BN HQ fixed draw (§3.3.1a).

**Modifier breakdown** visible under each HQ — labeled, color-coded (green = bonus, red = penalty).

**"Other +/–" field removed.** All standard modifiers are explicit.

### UI

- Turn and Activity Level moved to sticky header — editable from any tab
- Activity auto-feeds No Contact +1 into every command calculation
- Input field styling standardized across all tabs

### Save Compatibility

Full backward compatibility with v3.0 saves. Old formats migrate on load.

---

## v3.0 — Full Tracker Rebuild (2025-02-22)

Complete rebuild from Excel to single-file HTML/React. All tracking in one browser tab.

### Core Features

- **11 tabs:** Setup, Turn Sequence, Command, Units, Combat (NCM), Enemy, Fire Missions, Assets/Comms, Map & Contacts, Battle Journal, Campaign Log
- **All 4 campaigns, 31 missions** with pre-loaded data: Normandy (7), Heartbreak Ridge (8), Naktong River (7), Vietnam (9)
- **Mission auto-setup:** Unit ammo counts, fire mission agencies/draws/missions, HQ experience levels — all populated from mission data on "New Mission"
- **Complete turn sequence** with phase-by-phase checklist filtered by mission type (Offensive/Defensive/Patrol)
- **NCM calculator** with 3-step structure matching Player Aid layout
- **Command Tracker** with per-HQ draw entry, 10-turn × 6-command grid
- **Unit tracker** with status, cover, VOF, location, experience for all TO&E units
- **Fire Mission tracker** with per-agency draw numbers (Arty/Mtr/CO/PLT/FAC columns as applicable)
- **Radio/Comms tracker** and **Asset/Pyrotechnics tracker**
- **Card Tracker** (map grid) with terrain, C&C, PC, cleared, US/Enemy occupancy, cover, notes
- **Battle Journal** with per-entry turn, phase, event, unit, detail, result, notes
- **Campaign Log** with mission results and replacement tracking

### Save System

- Auto-save to localStorage every 5 minutes
- 6 manual save slots with labels and timestamps
- JSON export/import for backup and sharing
- Full state preservation across browser sessions

### Technical

- Single HTML file — no server, no build step, no dependencies beyond CDN React/Babel
- PWA-capable with service worker for offline use
- Installable on mobile (iOS/Android home screen)

---

## v2.0 — Excel Tracker (2025-02-21)

Multi-sheet Excel workbook with formulas and dropdown menus.

- 12 sheets: Setup, Command, OOB & Units, Map & Contacts, Combat, Weapons & Ammo, Comms & Assets, Enemy, Battle Journal, Campaign Log, Reference Tables, Data Tables
- 170+ formulas, named ranges for dropdown consistency
- Command draw modifier formulas (experience, visibility, tactical situation)
- Save limits auto-adjusting by experience and day/night conditions
- VLOOKUP for terrain-to-C&C mapping
- 43-action dropdown from §4.2, 46-unit roster, 29 terrain types, 31 missions
- All text-formatted to prevent Excel date conversion on unit IDs

---

## v1.0 — Initial Concept (2025-02-21)

Basic Excel spreadsheet for tracking Fields of Fire game state. Manual entry, no formulas.

---

## Verified Against

- Fields of Fire Deluxe 3rd Edition Series Rules (GMT Games, © 2024)
- Player Aid: Charts & Tables 1 and 2
- Player Aid: Enemy Activity Check Hierarchy
- Campaign books: Normandy, Heartbreak Ridge, Naktong River, Vietnam
- Rules §3.3, §4.1.2, §5.3, §6.4, §7.10

---

*Fields of Fire is © GMT Games. This is a fan-made play aid.*
