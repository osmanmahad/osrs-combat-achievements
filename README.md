# OSRS Combat Achievements Tracker

A single self-contained HTML page: look up an Old School RuneScape player and see exactly which
Combat Achievement tasks they have left, grouped by tier, with a "fastest path to the next reward
tier" planner.

No backend, no build step, no dependencies beyond a browser — open `index.html` directly, or serve
it with any static file server.

## What it shows

- Total Combat Achievement points, current reward tier, and progress to the next tier
- An Easy → Grandmaster completion breakdown
- A "Fastest Path" planner: the cheapest remaining tasks that would close the point gap to your next tier
- The full remaining-task list, grouped by tier, filterable by tier / search / exempt / completed,
  sortable by tier order or by rarity
- A per-task completion-rate ("rarity") badge — e.g. "1.8% of players" — sourced from the OSRS Wiki

## Data sources

- **Player progress**: [RuneProfile](https://runeprofile.com)'s public API
  (`api.runeprofile.com/v1`). This only works for players who've synced at least once via
  RuneProfile's RuneLite plugin (or a manual upload).
- **Completion rates ("rarity")**: scraped client-side from the OSRS Wiki's
  [Combat Achievements/All tasks](https://oldschool.runescape.wiki/w/Combat_Achievements/All_tasks)
  page, joined to RuneProfile's task data by task ID. Cached in the browser for 24 hours.
- **Reward-tier point thresholds** (Easy=41pts ... Grandmaster=2,697pts) are hardcoded constants
  sourced from the OSRS Wiki at the time this was written, and may need updating if Jagex adds
  enough new tasks that the wiki recalibrates them.

## Usage

Just open `index.html` in a browser, type a username, and press Enter or click Look Up.
