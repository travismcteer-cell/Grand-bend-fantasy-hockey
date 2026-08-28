# Grand Bend Fantasy Hockey Draft

## Purpose
A mobile-friendly fantasy hockey snake-draft decision-support app with a Grand Bend beach + hockey theme.

## League rules
- 12 teams, snake draft
- 2 C, 2 LW, 2 RW, 2 D, 2 G
- 4 unrestricted spares
- Spares cannot be drafted until all 10 starting slots are filled
- Skater categories: G, A, PIM, PPP, HIT, BLK
- Goalie categories: W, SV, GA (lower GA is better)

## Current app
`index.html` is a self-contained browser app. It currently contains a real 250-player 2026-27 draft pool based on Daily Faceoff consensus ranking/position/team information and Yahoo ADP. Detailed category projections still need to be merged; do not invent them.

## Important implementation requirements
- Multi-position players must occupy exactly ONE roster slot at a time. Do not count a C/LW player as filling both positions.
- Recommendations should ultimately combine projected category contribution, positional value above replacement, roster/category fit, scarcity, ADP, and probability a player survives to the user's next snake pick.
- Keep category-level projected values available; do not reduce the dataset to only a final ranking.
- Prefer stable player IDs for data joins rather than names.
- Preserve the Grand Bend beach/hockey visual design and mobile usability.

## Data direction
- Daily Faceoff: 2026-27 projections/consensus/ADP where appropriate and permitted.
- MoneyPuck: permitted published historical downloads, with attribution where required.
- NHL stats/API endpoints: historical/current stats and player metadata.
- Clearly distinguish projections, historical proxies, ADP, and temporary placeholders.

## Next development priorities
1. Test `index.html` in a normal browser and fix any UI/runtime issues.
2. Replace the current greedy multi-position assignment with a correct roster-slot assignment algorithm.
3. Merge real category projections for G/A/PPP/HIT/BLK and goalie W/SV/GA.
4. Add a defensible PIM projection/proxy and label its provenance.
5. Recalculate category z-scores and positional VAR for this league's exact roster rules.
6. Improve pick urgency using the user's draft slot and ADP/availability distribution.
7. Deploy via GitHub Pages so the app has a normal URL.
