# Product Development Framework site: project notes

A one-page site that explains Cru Campus Ministry's Product Development Framework: why it matters, the six stages and the roles at a glance, "Ask Bright" (a chat box that answers questions straight from the framework docs), ways to learn it, a toolbox of templates, and 20 flashcards.

Live at https://mpf.crutastic.com (was productdevelopment.crutastic.com until 2026-11-09; also https://markmichal.github.io/pdf-framework-site/). GitHub repo: markmichal/pdf-framework-site (public). `_dev/HANDOFF.md` is the dated session log.

## Why Mark built this
From his Projects Hub card: "So a team can see the whole process at once instead of hunting through slide decks." What he learned: "Connected Claude to ChatGPT to make better images, and built a chat bot that answers questions straight from the document."

## How to use it
- Run locally: `python3 -m http.server 8765`, then open http://localhost:8765 (flashcards need a server).
- Publishing: edit `index.html`, commit, push to `main` (with Mark's OK); Pages rebuilds in 1 to 2 minutes.
- Ask Bright's script is deployed separately by Mark (`_dev/apps-script/SETUP-ASK-BRIGHT.md`). Changing the script: Deploy > Manage deployments > pencil > New version, so the URL stays the same.

## Files
- `index.html`: the whole site. `flashcards.json`: the cards. `assets/`: Bright the mascot, stage circles and role icons, Cru brandmark. `CNAME`: the domain.
- `_dev/`: the approved mockup, the Ask Bright Apps Script source, the original build handoff, and HANDOFF.md. Not published.
- `README.md`: public front page. `AGENTS.md`: rules for any AI helper. `CLAUDE.md`: the full working notes.

## Decisions
- 2026-10-09: Built from the approved mockup as one `index.html`, no framework. Nav collapses under 960px. Flashcards copy says "Twenty". Site strips `**` from Ask Bright answers.
- 2026-10-09: Custom domain productdevelopment.crutastic.com.
- 2026-10-12: Mark's and Lorenna's names are email links with a pre-filled subject.
- 2026-11-07: Ask Bright moved to a new Apps Script in Mark's Cru Google account (a personal-account script can't read the Cru Drive docs). New key "Ask Bright 2" from Mark's own Claude Console org, never expires (Mark's choice for light apps like this); old key disabled. Identity federation doesn't fit Apps Script or GitHub Pages sites.
- 2026-11-09: Renamed to "Ministry Product Framework" (was Product Development Framework) on the page, tab title, link preview, and email subjects.
- 2026-11-09: New address mpf.crutastic.com (GoDaddy CNAME to markmichal.github.io). Mark chose to let the old productdevelopment address stop, no redirect; its GoDaddy record removed. Workvivo post assets for the Campus Innovation page are in Drive: CRU > EVENTS & PROJECTS > 2026-2027 > Ministry Product Framework > Workvivo Post.
- 2026-11-07: Every app's key and swap steps are listed in ~/Projects/command-center/API-KEYS.md.

## Ideas for later
- Delete the unused personal-account copy of the Ask Bright script (optional, from HANDOFF.md).

## History
- 2026-10-09 to 10-12: Built, Ask Bright connected, domain set, small copy fixes.
- 2026-11-07: Ask Bright key renewed and moved to the Cru-account script.
- 2026-11-09: Project kit added (AGENTS.md, NOTES.md, backup to Drive). CLAUDE.md was left alone because it had an uncommitted edit; it can become a short pointer to AGENTS.md later.
