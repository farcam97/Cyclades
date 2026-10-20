# Graphics update 17.0 preview

This preview implements the approved graphics and usability changes on top of 16.2. New three-player campaigns use the supplied continuous illustrated map: 14 land territories, 14 sea areas, 24 building sites, three churches, ten single printed offerings and two double offerings. Coastlines and the drawn dividers define hit areas and connections. Existing saved boards and other player counts retain their original geometry. Randomized gods remain deliberately deferred.

## Implemented

- Back and Confirm are compact text rectangles. Back stays left and Confirm right; other illustrated actions keep their medallions.
- Printed offering plaques use light gray. Additional prosperity turns the combined-count plaque white, reverting when the extras are removed. Printed values remain separate from the live total.
- An eighth selectable faction, Owl, uses deep maroon and cream. Existing factions and the 2–6-player limit are retained. Older saved faction-selection orders can select the new owl. Save validation accepts the new valid faction index and still rejects out-of-range factions.
- Map ownership emblems have thick faction-colored rings, with a narrow light backing to help dark colors contrast against terrain.
- Both shops already shuffled their permitted decks at new campaign creation. Tests now verify different new-game orders and preserve deck order across rendering and saves. Refresh, discard and reshuffle rules are unchanged.
- Bottom navigation uses the supplied gold artwork in normal mode and silver artwork in dark mode. All six destinations retain their functions, accessible names and keyboard controls. The selected destination glows softly.
- Building art is taken from the supplied transparent building sheet: Fortress, University, Temple, Port, Metropolis, Church. The university is a newly generated isolated adaptation with all blue and gold areas made white. Empty building patches use the black silhouette from the supplied image, with its background and shadow filtered out. A building replaces its site's silhouette. Churches occupy the supplied map's gray markers and grant Priestess cards through the existing land-claiming rules; they do not consume a building site.
- Unavailable actions show nonmodal explanations, including the required god, money, action limit, occupied Apollo, or placement/reserve restrictions. Disabled purchase controls never execute their original purchase action.
- Map view controls expose adjustable piece size and temporary name hiding. Crowded placement can reduce piece sizes to avoid covering construction sites and offerings. Counts remain visible when names are hidden.
- Battle breakdowns show ships or troops/mercenaries, hero/creature strength, buildings/other bonuses, die results, authoritative totals and named casualties. Hero rules expand separately. Results keep the strength snapshot from before casualties, preventing shrinking armies from changing the displayed round totals.
- Automatic, High and Low graphics settings are independent of Reduced motion and the existing sound controls. Automatic uses browser device-memory/CPU hints where available; absent hints default to High. Low reduces model resolution, redraw rate and decorative effects. Performance mode remains a stronger existing override.
- Hero card touch fixes address both inherited pointer-events disabling map figures and touch-generated clicks being retargeted onto the newly opened popup's Close/Sacrifice button. Only the generated follow-up click is consumed; the next real tap and keyboard controls remain active. The old orange image outline is removed.

## Experimental 3D ships

The user's original binary STL contains 15,536 triangles. It is loaded locally, normalized and uploaded once to a shared WebGL buffer. Every faction shares the shape with its actual faction color. No runtime network service or third-party rendering dependency is required.

One WebGL context renders into one shared atlas and reuses canvases for map, naval battles, fleet inspectors and other fleet artwork. The renderer pauses offscreen/hidden ships and stops idle updates under Reduced motion, Performance mode or disabled animations. High updates at most 24 times/second; Low at most 10. Idle movement is a subtle roughly 16-second bob. Sailing uses the engine's actual presentation step before movement is committed, with a wake, faction-colored models and filtered water noise. Cancellation removes transient figures without changing game state. Sound follows the existing master/Battle controls and stops when muted or backgrounded. Visual/audio variation does not consume gameplay random numbers.

Where WebGL is unsupported or fails, the existing fleet artwork remains usable. Device/browser context restoration is handled. These are real 3D model renders, not prerecorded ship sprites.

## Validation and limits

All 47 production browser checks pass. They cover the new map graph, marker/site placement, church rewards, exact map save/reload and geometry validation, other player counts, new graphics, repeated hero touch input, owl save compatibility, shop order, naval movement/cancellation, fallback rendering and audio, alongside existing save/import/gameplay tests. Automated standard and owl campaigns reach a winner. Screenshots are desktop Chromium captures at phone/tablet sizes, not physical-device captures. The APK uses the same separate local preview identity as 16.2, version code 19, version name 17.0-preview. Export a save before updating installations.

No phone FPS, battery, temperature or real-device WebGL claims have been established. Physical Android testing is still required. The old 16.1 benchmark is not a performance benchmark of this release.

The source-provided engine suites retain two documented inherited failures: the old captured-Metropolis bonus expectation and the obsolete performance/input harness. Their assertions remain enabled.

## Map authoring

`web/map-three-player-data-v17.js` and `tools/map-data/three-player-map.json` contain the traced static geometry and source image checksum. `tools/trace-three-player-map.py` reproduces these files from the original image, using color-based coastline masks plus reviewed river/foam divider traces. It generates numbered region review images under `artifacts/`. Its optional authoring dependencies are NumPy, SciPy and OpenCV; they are not app or Android build dependencies. Same-type connections follow traced dividers, so touching at a corner does not create a move. Static geometry is checked when importing a custom-map save.
