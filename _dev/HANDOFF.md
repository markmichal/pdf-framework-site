# Handoff

## 2026-10-09
- Built the full site from the approved mockup (`_dev/design-reference/`). Checked at 360, 768, and 1280px: no horizontal scroll, tap targets 44px+.
- Real Cru brandmark (full color) used in the nav.
- Mockup said "Ten quick cards" in Flashcards; changed to "Twenty" since there are 20 cards.
- Toolbox uses the six real tools from the handoff; "Idea" tags removed. Icons are all yellow.
- Nav collapses to a Menu button under 960px (a bit above the 900 in the brief, so the six links plus the button never crowd).
- Open: Ask Bright is not live yet. Mark deploys `_dev/apps-script/ask-bright.gs`, then the web app URL goes into `ASK_URL` in index.html.
- Open: DNS CNAME for productdevelopment.crutastic.com, and Pages custom domain / Enforce HTTPS.
- Ask Bright deployed (Apps Script under Mark's Cru account) and ASK_URL set in index.html. Site strips `**` from answers since the model sometimes bolds despite the rules. Changing the script later: Deploy > Manage deployments > pencil > New version (URL stays the same).
