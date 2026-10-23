# 17.1 Preview

- Retreat choices stay inside combat rather than opening the map after each roll. Battle dialog and bottom navigation are shorter.
- Combat shows the contested region's basic building counts, Metropolises and cornucopias separately from combat strength.
- Movement previews use the moving faction's color and clear before travel/combat, including cancellation paths.
- Hero and creature shop actions keep text buttons without circular action art; creature portraits return to their compact size.
- Generic computer hero-recruitment narration is removed; the specific recruited hero is still named.
- Match statistics dismisses the victory/defeat overlay. The map Aa shortcut is removed; its preferences remain in Settings.
- Buildings collapse briefly when removed; transferred buildings do not trigger demolition. Motion preferences are respected.
- New maroon/light-cream Owl emblem, troop and fallback fleet artwork.
- Zeus top-deck ordering is covered by regression tests: declining preserves deck order; playing consumes only the top card and costs one gold. An empty deck no longer consumes the peek. The reported turn-order concern needs further clarification.

This update is based on the 17.0 workspace. The separately discussed replacement map, faction image sprites, portraits and cloud treatment are not included in this patch.

Validation: 51 production browser checks; Android signature/alignment and packaged-asset verification. No physical Android testing. Two inherited source-suite discrepancies remain documented in the validation report.
