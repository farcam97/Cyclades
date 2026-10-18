# Interface update 16.2

This update implements the user's selected interface changes. The campaign save schema remains version 5. Territory polygons, adjacency, construction sites, victory conditions and existing Apollo rule are preserved.

1. Game actions use a shared illustrated medallion and label. Existing fleet/recruit/end-turn artwork is reused; other actions have matching vector medallions. Close, Settings, zoom, navigation and stepper utilities remain compact.
2. Dark mode uses white text and brighter accents, including dark battle surfaces behind the text.
3. Battle results wait for Continue after each round and Return to map after the outcome. This remains true with animations disabled or performance mode enabled. Automated simulations bypass reading pauses. The preference can be changed in Animation settings.
4. Turn emblems have a two-second removal deadline. Narration hides after two seconds and no longer copies itself into a persistent map prompt.
5. The generic creature announcement and preliminary calls-upon log were removed. Creature-specific effect descriptions and Chronicle entries remain.
6. Confirm/Continue actions align on the right of their button row. Back/cancel controls remain before them.
7. Triton's existing eligible-building choices are exposed on the map. Eligible buildings glow in their building color, ineligible buildings are dimmed, and the exact building must be confirmed before the engine's existing transfer/placement flow continues.
8. Hero recruitment names the hero in a brief announcement and the Chronicle.
9. The map layout reserves offering plaques and construction sites, checks figure footprints against territory geometry, and considers neighboring territories. Crowded forces use labeled counts instead of spreading figures across borders. Positions are cached; zooming does not repack the board.
10. Only the settings Close button stays pinned while the remaining header/content can scroll.
11. The anonymous offering-symbol cover rectangles were removed. Each resource location now has an explicit white-backed cornucopia badge with the current count, including a visible zero when a printed location has been depleted. Badges render above figures, and placement reserves their footprints.
12. Top building counters use their building colors for icons and values, brightened in dark mode.
13. Existing tile art is retained. Tile edge blending and softer sea boundary strokes reduce the rigid grid; high-contrast boundaries remain available. No connections or area shapes are changed.
14. The title is hidden before the initial intro mounts, eliminating the initial title flash. The skippable 6.5-second opening uses the existing ocean/god/fleet art, mist, lightning and a timed title reveal. Reduced motion uses a shorter static opening.
15. Battle figures now have anticipation, movement, impact and recovery phases. Staggered motion, arcing projectiles, spray/dust, scene movement and impact shake are tied to the existing round presentation. No extra game random draws are used for visual variation. Reduced-motion and performance preferences remain respected.

## Validation and limits

The browser suite checks dark text/surfaces and counter colors, scrolled Close access, resource counts, crowded footprints, confirmation alignment, expiring narration, manual battle results, visible cinematic animation, direct Triton building selection and transfer, intro coverage/skip, named recruitment, and unchanged map topology. It also retains the earlier save/import/gameplay checks. Screenshots are browser captures, not Android device captures.

The source-provided v16 feature/dense-layout, targeted, interaction, integration, core campaign, Maelstrom campaign and SVG reconciliation suites pass. The two inherited discrepancies are still reported rather than disabled: an older captured-Metropolis bonus expectation and an obsolete performance harness that does not load the current input scripts.

Android package `com.aegean.cyclades.preview` is version 16.2/code 18, signed with the same local preview key as 16.1. It can update that preview installation. It does not update the separately signed original Cyclades app. Export a save before changing installations. APK signatures and alignment are checked, but physical Android behavior and device performance have not been validated.

The 16.1 performance report is historical and is not a benchmark of the new layout/animation implementation.
