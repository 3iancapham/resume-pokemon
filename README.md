# Fire Résumé Version

Bianca Pham’s walkable Pokémon-inspired résumé: lime-green Game Boy Color hardware styling, FireRed/LeafGreen-inspired color art, eight career gyms, and photo-informed manga trainer characters.

Open `index.html` in a browser, or run `python3 -m http.server 4173` and visit http://localhost:4173. No build dependencies are required. `vercel.json` enables clean URLs for static deployment. Published source: https://github.com/3iancapham/resume-pokemon.

## Play

Click the console. Arrow keys or WASD walk; Z/Space interact; X/Escape goes back; Enter opens the menu; Shift opens the map. Pointer controls support phones. The Game Boy Color shell keeps its proportions at every viewport.

Walk into a gym, choose FIGHT, and explore each achievement move to earn a badge. The map lets you fly to any gym. Progress saves locally when browser storage is available. A complete collection opens the Hall of Fame. Stealth Bianca, your past-self rival, appears at the introduction and after four and seven badges. Press B to skip; completed encounters are saved.

The strategy guide unlocks one job per badge. A complete text résumé remains accessible without playing. Contact links open an email composer or LinkedIn; the game sends no messages itself.

## Artwork and content

All runtime code, content, styles, and generated sprite atlases are embedded in `index.html`. External Google Fonts enhances page typography when online; game text uses an inline bitmap alphabet. The PNGs in `assets/` are editable source copies and are not required alongside the standalone HTML.

The latest CZ résumé supplies career facts and relocation language. `REBUILD-PROMPT.md` supplies the original mechanics and cast. The user’s subsequent revision overrides the landscape GBA shell and code-only artwork constraints. `Small-Avatar.png` supplies Bianca’s current likeness, replacing the earlier bangs description. The supplied photo itself is not embedded in the game.

Generated assets:
- `assets/trainer-atlas.png` — Bianca and eight leader caricatures.
- `assets/bianca-companion-atlas.png` — Bianca’s battle entrance and portrait, plus the husky battle sprites.
- `assets/stealth-bianca.png` — past-self rival and stealth-company leader.
- `docs/art-prompts.md` — generation prompts and integration notes.

The cast and dialogue are fictional game framing, not endorsements. `CARD.phone` can optionally enable a phone row. Update `DATA` to edit the résumé and `BRIEF_MOVES` for concise combat summaries.

## Verification

`tests/playthrough.cjs` checks all eight gym encounters, guide unlocks, save/reload, menus, mobile layout, and keyboard focus. `tests/walkability.cjs` checks walking routes to all buildings and collisions. `tests/art-revision.cjs` checks six viewport sizes, constant shell proportions, art loading, and battle-screen compositing. The test scripts reference the bundled local Playwright/Chromium runtime; replace those paths to run on a different machine.

`window.__game` exposes `tick`, `press`, `down`, `up`, `teleport`, `snapshot`, `drawMap`, `badgeSheet`, `castSheet`, `portrait`, plus state, position, badge, battle, and art-load snapshots.
