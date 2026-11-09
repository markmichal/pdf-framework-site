# Handoff

## 2026-11-09
- Renamed to "Ministry Product Framework" (was Product Development Framework): page heading, tab title, link preview text, email subject lines, README. Web address unchanged on purpose so old links work. Pushed with Mark's OK.
- Made a Workvivo post (picture + text) for the Campus Innovation page. Saved in Drive: CRU > EVENTS & PROJECTS > 2026-2027 > Ministry Product Framework > Workvivo Post.
- New address mpf.crutastic.com: Mark added the GoDaddy CNAME and deleted the old productdevelopment record; GitHub Pages custom domain switched, HTTPS enforced, checked live. Projects hub card renamed and relinked. Workvivo picture and text use the new address.
- Open: Ask Bright answers from the framework docs; if those still say the old name, Bright may too. 

## 2026-11-07
- Ask Bright's 30-day API key was expiring 2026-11-08. Mark made "Ask Bright 2" (Never expires, Default workspace).
- The script holding the old key was never found. A personal-account copy can't read the Cru Docs ("Action not allowed"). So Mark made a new "Ask Bright" script in his Cru account with the new key, deployed it (Anyone), and ASK_URL now points there. Tested from outside: answers.
- Correction: the 2026-10-09 note saying the script was in the Cru account was wrong at the time; it is now.
- Done: old "Ask Bright" key disabled, live site retested and answers on the new key. Open: delete the unused personal-account copy (optional). API keys helper in command-center.

## 2026-10-09
- Built the full site from the approved mockup (`_dev/design-reference/`). Checked at 360, 768, and 1280px: no horizontal scroll, tap targets 44px+.
- Real Cru brandmark (full color) used in the nav.
- Mockup said "Ten quick cards" in Flashcards; changed to "Twenty" since there are 20 cards.
- Toolbox uses the six real tools from the handoff; "Idea" tags removed. Icons are all yellow.
- Nav collapses to a Menu button under 960px (a bit above the 900 in the brief, so the six links plus the button never crowd).
- Open: Ask Bright is not live yet. Mark deploys `_dev/apps-script/ask-bright.gs`, then the web app URL goes into `ASK_URL` in index.html.
- Open: DNS CNAME for productdevelopment.crutastic.com, and Pages custom domain / Enforce HTTPS.
- Ask Bright deployed (Apps Script under Mark's Cru account) and ASK_URL set in index.html. Site strips `**` from answers since the model sometimes bolds despite the rules. Changing the script later: Deploy > Manage deployments > pencil > New version (URL stays the same).
