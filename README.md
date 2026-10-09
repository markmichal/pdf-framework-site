# Product Development Framework site

One page, static site for Cru Campus Ministry's Product Development Framework. Hosted on GitHub Pages from `main`, at framework.crutastic.com.

## Where things live

- `index.html`: the whole site (inline CSS and JS, no build step).
- `flashcards.json`: the 20 flashcards. Edit the text here, no code changes needed.
- `assets/`: Bright the mascot (`mascot/`), stage circles and role icons (`framework/`), Cru brandmark (`brand/`).
- `CNAME`: the custom domain.
- `_dev/`: design mockup, the Ask Bright script, and handoff notes. Not published (GitHub Pages skips underscore folders).

## Updating Ask Bright's URL

At the top of the script in `index.html`:

```js
const ASK_URL = 'PASTE_APPS_SCRIPT_URL_HERE';
```

Replace the text in quotes with the Apps Script web app URL, then commit and push. Setup steps for the script are in `_dev/apps-script/SETUP-ASK-BRIGHT.md`. If you only change the script (not the URL), redeploy as a new version of the same deployment and the URL stays the same.

## Updating the toolbox or learn links

Search `index.html` for the link text (for example "Project charter") and swap the `href`.

## Run it locally

```bash
python3 -m http.server 8765
```

Then open http://localhost:8765. (Flashcards need a server, they will not load from a double-clicked file.)
