# Jungle Island v0.5 JFG — Well, Goblin Shadow Fix, and Palm Tree Update

This package is a safe visual-only update for Jungle Island.

## What changed

- Keeps the approved lighter isometric stone well sprite.
- Removes the tiny backpack test from the goblin sprites.
- Keeps the goblin shadow/underlay cleanup so the weird dark shadow is hidden.
- Adds new cosmetic palm trees at:
  - `(16,15)`
  - `(17,15)`
  - `(17,16)`
  - `(12,3)`
  - `(12,2)`
- Uses the same palm sprite behavior as the existing palm trees.

## Palm tree behavior

The new palms are cosmetic only. They do not block movement, change resources, change rewards, change water, or change AI behavior.

Palm sprites are allowed to visually overlap nearby grid squares. Agents can still walk through/over the underlying square normally according to the existing tile rules, and agent sprites should render above the palm when they overlap.

## What did not change

This update does not change:

- AI behavior
- Q-learning
- movement rules
- rewards
- resource logic
- water logic
- map generation
- pathing
- day/click timing
- agent stats
- export/logging behavior

## Our update rule

Every update should be delivered as a full replacement ZIP containing the complete working app file set:

- `index.html`
- `app.js`
- `style.css`
- `README.md`

Even when only one visual item changes, the full file set prevents accidentally mixing an old file with a new file.

## Phone/GitHub upload workflow

1. Download the ZIP.
2. Unzip it in the iPhone Files app.
3. Open the unzipped folder.
4. Upload the actual files to GitHub, not the folder itself.
5. Replace the existing `index.html`, `app.js`, and `style.css` in the live project location.
6. Commit with a clear message, such as:

   `Visual update: well, goblin shadow fix, palms`

7. Open the live GitHub Pages link and run the smoke test below.

## Smoke test after launch

Check these before considering the update successful:

- The island loads.
- The map is visible, not blank.
- The well appears as the lighter isometric stone well.
- The goblins do not have the tiny backpack.
- The weird dark goblin shadow/underlay is gone.
- Palm trees appear at `(16,15)`, `(17,15)`, `(17,16)`, `(12,3)`, and `(12,2)`.
- The new palm trees do not push grid squares out of place.
- Agent cards still update.
- Pause/Play still works.
- Agents still move normally.
- No browser crash or blank screen appears.

## Rollback plan

Keep the previous working build in a folder named something like:

`LAST GOOD BUILD — DO NOT DELETE`

If the live page breaks, re-upload the previous working `index.html`, `app.js`, and `style.css`.
