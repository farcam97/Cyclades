# Cyclades 18.0 Preview

This release combines the supplied graphics with the battle and touch fixes.

- Replacement three-player board traced from the guide: 14 land regions, 19 sea regions, 25 construction spaces, three permanent churches, 11 single and two double offering locations. Colored guides are invisible. Existing saves keep their original map.
- Churches replace Priestess markers. They cannot be constructed, demolished or stolen, and do not reduce normal building capacity. No church counter appears at the top.
- Clean map exterior is transparent; the printed Priestess figure is removed. Optional slowly drifting edge clouds default off and pause with Reduced Motion.
- Red Scorpion is replaced by the red/cream Frog design: matching troop, emblem, static ship and eight sailing headings. One heading mirrors the matching opposite view.
- Cream-sailed Lion ships, gold-armored Lion troop with natural skin, lavender Otter troop, and gray Ox troop. Troops remain motionless when stationary. Other factions retain existing flat ship art.
- All experimental 3D ships are replaced by image sprites. Ships bob slowly; sailing uses directional art, wakes and the existing water sound/mixer controls.
- Six supplied god portraits replace their previous images throughout the game. Portrait rims and protruding details are preserved.
- Separate clean building sprites and front-facing top counters; University is white/light gray. Metropolis is larger and its larger footprint is reserved by the placement system.
- Hero touch targets work in screen pixels when zoomed out. Faction artwork changes invalidate map/layout caches.
- No generic computer "recruits a Hero" announcement; specific hero announcements remain.
- Shop actions no longer have circular medallions. Creature images return to compact sizing. Bottom bar and battle dialog are shorter.
- Battle choices, including retreat destinations, stay inside the battle screen. The contested region's building/cornucopia counts are shown. Travel previews clear before travel/combat and use faction colors.
- Buildings show a brief demolition animation when removed. Transfers do not cause a demolition cue. Motion preferences are respected.
- Statistics dismiss the defeat/victory overlay. The map Aa shortcut is removed; settings retain readability controls.
- Zeus's deck order is regression-tested. Declining preserves the top card; playing consumes it and costs one gold. Empty decks do not consume the peek. No additional timing change was made without a reproducible example.

The replacement Medusa picture was not included in either Uploaded ZIP, so Medusa retains its previous artwork. Random-god setup remains deferred.

Validation: 58 production browser tests pass; Android signature, alignment and bundled-asset checks. No physical phone testing or phone FPS/battery claims. Two inherited source-suite discrepancies remain documented separately.
