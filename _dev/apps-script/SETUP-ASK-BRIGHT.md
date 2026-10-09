# Setting up Ask Bright (Apps Script)

About 15 minutes. Do this while Claude Code builds the site.

## 1. Create the script
1. Go to script.google.com and click **New project**. Name it "Ask Bright".
2. Delete the starter code, paste in all of `ask-bright.gs`, and save.

## 2. Add your API key
1. Click the gear (**Project Settings**) on the left.
2. Scroll to **Script Properties**, click **Add script property**.
3. Property: `ANTHROPIC_API_KEY`, Value: your Claude API key. Save.
4. Optional extras:
   - `DAILY_LIMIT`, e.g. `300`, caps questions per day.
   - `LOG_SHEET_ID`, the ID of a blank Google Sheet, logs every question and answer so you can see what people ask.
   - `MODEL`, only if you want a different Claude model.

## 3. Test it
1. Back in the editor, pick `testAsk` from the function dropdown and click **Run**.
2. Approve the permissions (it needs to read your Docs and call an outside service).
3. Check the log at the bottom. You should see Bright's answer about the three choices at the end of Iterate.

## 4. Deploy
1. **Deploy > New deployment**, click the gear, choose **Web app**.
2. Execute as: **Me**. Who has access: **Anyone**.
3. Click **Deploy** and copy the **Web app URL**.
4. Give that URL to Claude Code (or paste it into `ASK_URL` in index.html).

## Updating later
- Changed the manual? Nothing to do. Bright re-reads it at least every 6 hours.
- Changed the script? **Deploy > Manage deployments**, pencil icon, Version: **New version**, Deploy. The URL stays the same.

## Good to know
- Your API key lives only in Script Properties. It never touches the website or GitHub.
- "Anyone" access means anyone with the URL can ask questions. That's why there's a daily cap.
- Cost is roughly a penny or two per question. Prompt caching makes back to back questions cheaper.
