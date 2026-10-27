# Lancer Action Board

A clickable turn diagram for Lancer. Each player picks their callsign tab and sees exactly what their mech can do with a Move, Full, Quick, Overcharge, Free action, Reaction, or Protocol.

## Files

```
index.html        the app
Milkman.json      COMP/CON pilot exports, one per player,
Shrimpboat.json   named after the callsign
Tsar.json
Bluedog.json
```

File names on GitHub Pages are case-sensitive. The page tries `Milkman.json`, `milkman.json` and `MILKMAN.json`, so any of those spellings work.

## Setup

1. Create a repository and add `index.html` plus the four pilot files.
2. In the repository go to **Settings → Pages**, set **Source** to *Deploy from a branch*, pick `main` and `/ (root)`, and save.
3. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

Each tab has its own link to hand out, for example `.../#Milkman` or `.../#Tsar`.

## Updating a pilot

When a player levels up or changes their build:

1. In COMP/CON, open the pilot and use **Export** to save the pilot JSON.
2. Rename it to the callsign (for example `Shrimpboat.json`) and replace the old file in the repository.
3. Players press **Refresh**. GitHub Pages usually takes a minute or two to publish a new commit.

## Changing the squad

The callsigns are listed near the top of the script in `index.html`:

```js
const SQUAD = ["Milkman", "Shrimpboat", "Tsar", "Bluedog"];
```

Add, remove or rename entries and the tabs follow.

## Testing on your own computer

Browsers block a page opened straight from disk from reading the JSON files. Run a small local server in the folder instead:

```
python3 -m http.server
```

Then open http://localhost:8000.
