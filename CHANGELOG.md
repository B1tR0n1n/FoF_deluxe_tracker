# Fields of Fire — Deluxe Mission Tracker v3.1 Changelog

Single-file HTML tracker for Fields of Fire Deluxe (GMT Games, 3rd Edition).
No install. Works in any browser. Auto-saves to local storage.

---

## Summary

v3.1 is a rules-accuracy pass. The NCM calculator has been restructured against the official Player Aid (Infantry Combat Modifiers table), and the Command Tracker — which previously had non-functional modifier fields — now calculates automatically per §4.1.2. Several issues flagged by the BGG community have been addressed, and one community correction (Grenade Miss stacking) was itself corrected against the Player Aid.

---

## NCM Calculator

**All Pinned (+2) now overrides all other VOF.** Previously it competed in the lowest-value pool — selecting All Pinned alongside Heavy would ignore All Pinned and use –3. Checking All Pinned now disables all other VOF inputs. PA: *"Overrides normal VOF."*

**Grenade (G!) is cumulative.** Replaced the single –3/–4 dropdown with a count input. Enter total G! markers and how many hit at –4. Multiple grenades stack: 2× G! at –3 = –6. PA: *"G! VOF are cumulative with each other."*

**Sniper (–3) moved from Step 1 (VOF) to Step 3 (Other Modifiers).** PA lists Sniper under "Other." Includes reminder that rest of card resolves under S VOF.

**Rocket/Grenade Miss reverted to checkbox (–1, once per card).** Was incorrectly changed to a numeric input allowing multiples based on a community suggestion. PA explicitly states: *"Apply only once per card."*

**Stacking penalty reworked.** Was a flat –1 checkbox applied to all VOF types. Now a numeric input (–1 per step over 3 under cover), and only active when G! or Incoming! VOF is present. Grayed out otherwise. PA: *"Apply only to G! & Incoming VOF."*

**Concentrated Fire unchanged.** Numeric input (–1 each) is correct. PA: *"Can apply multiple times to target."*

**Exposed (–2) confirmed.** Not on the PA summary card but verified in §6.4 and worked examples. Applies to any unit that moved to an adjacent card.

**Incoming! and Air Strike! inputs restricted to negative values.** These are VOF modifiers — they should never be positive.

**Critical Hit / Hit Effect reference added.** Collapsible panel below the Final NCM result covering Combat Resolution (MISS/PIN/HIT), Hit Effect letter codes with severity hierarchy (§6.4.3), and Critical Hit resolution steps (§6.4.4). Includes Grenade Critical Hit note (§7.10.3). Collapsed by default.

**NCM clamped to –4 / +6.** Shows unclamped value when clamping activates.

---

## Command Tracker

**All §4.1.2 modifiers now auto-compute.** The Pin, VOF, and Cover dropdowns existed in the previous version but did not feed into the Total calculation. They were cosmetic. Now wired:

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

**Cover is now a leveled dropdown:** None, +1 Basic/Foxhole, +2 Trench, +3 Bunker/Pillbox. Was Yes/No giving flat +1.

**Command minimums enforced:** Activation min 1 (§3.3.1), Initiative min 0 (§3.3.2), CO Staff Initiative fixed 1 no modifiers (§3.3.2c), BN HQ fixed draw no modifiers (§3.3.1a). Red indicator when clamping overrides.

**Modifier breakdown visible** under each HQ total — labeled and color-coded (green = bonus, red = penalty).

**"Other +/–" field removed.** All standard modifiers are now explicit.

---

## UI

**Turn and Activity Level moved to sticky header.** Editable from any tab. No more navigating to Setup to change Activity Level. Activity auto-feeds No Contact +1 into every command calculation.

**Input field styling standardized.** Brown background with brown borders on every editable field. Black background on everything else. Consistent across all tabs.

**Command Tracker card backgrounds** changed from brown panel to black to match Map and other tabs.

---

## Save Compatibility

Full backward compatibility with v3.0 saves. Old formats migrate on load automatically.

---

## Verified Against

- Fields of Fire Deluxe 3rd Edition Player Aid — Infantry Combat Modifiers
- Series Rules §3.3, §4.1.2, §5.2.3, §6.2.4, §6.4, §7.10.4
- BGG community corrections — thanks to **Shonai Dweller** for flagging NCM issues that prompted this audit (with one correction revised back per Player Aid: Grenade Miss is once per card, not stackable)

---

*Fields of Fire is © GMT Games. This is a fan-made play aid.*
