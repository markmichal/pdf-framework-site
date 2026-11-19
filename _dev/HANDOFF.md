# Handoff

## 2026-11-18
- New learning media, all made from the current manual (Maintain, Product Steward). Learn section now links: Claude's motion video with music ("Making Progress" from Mark's Music for Videos folder, spliced to fit, 1:40), Gemini Notebook's short podcast (1:19) and full podcast (25:53), and Claude's 14-slide Google Slides deck. All four live in the shared drive's Notebook LM tools folder next to the old ones, anyone with the link can view. Old files left in place, not linked.
- Fixed old names in pictures: the Canva light bulb ("Product Development Process", page 1) now says Maintain; the manual's bulb and timeline pictures were swapped for fixed versions (timeline: Maintain, Keep It Healthy, Product Steward). Copies in Drive: Ministry Product Framework > Manual Pictures.
- Gemini Notebook "Ministry Product Framework (Nov 2026)" holds the source for the podcasts and a 5:55 Gemini video (not used; it showed the old pictures).
- Open: Canva pages 2 to 9 of that design still say Monitor and Develop on the side buttons; the manual's how-to GIF shows the old doc title.

## 2026-11-17
- Naming decisions from the team meeting: phase 6 "Monitor" is now "Maintain", and the role "Product Lead" is now "Product Steward". Updated index.html, flashcards.json, the Ask Bright script prompt, the dev notes and the design mockup. Renamed two image files to match (bright-maintain, role-product-steward). The pictures have no words in them, so the art did not change.
- Changed the tag under Maintain from "Track and maintain" to "Keep it healthy" so it doesn't repeat the title.
- On a branch (rename-maintain-steward), not pushed to main. Needs Mark's OK to merge.
- Open: redeploy the Ask Bright script (Deploy > Manage deployments > pencil > New version) so it uses the new names. Also the Drive docs it reads were updated the same day.
- Parked for later (framework, not site): a support group for the steward, who owns the product, spiritual practices per phase, skills per phase.

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
