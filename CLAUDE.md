# Product Development Framework site

One page static site for Cru Campus Ministry's Product Development Framework. `index.html` has inline CSS and JS, no framework, no build step. Deployed by GitHub Pages from `main` root at https://productdevelopment.crutastic.com (also https://markmichal.github.io/pdf-framework-site/).

## Architecture (do not break these connections)

- **index.html**: everything. Sections in order: sticky nav, hero, Why it matters, Framework at a glance with Roles (one boxed unit), Ask Bright, Learn it your way, Toolbox, Flashcards, footer.
- **`ASK_URL`** at the top of the script: the Google Apps Script web app that powers Ask Bright. While it still says `PASTE_APPS_SCRIPT_URL_HERE` the box shows "Ask Bright is almost ready". The request is a POST with `Content-Type: text/plain` (avoids a CORS preflight, which Apps Script can't answer). Response is `{answer}` or `{error}`.
- **flashcards.json**: loaded with `fetch`, so test through a local server, not `file://`.
- **_dev/**: mockup (`design-reference/`), Apps Script source (`apps-script/`), original handoff. Underscore folders are skipped by GitHub Pages. Do NOT add `.nojekyll`.
- **CNAME**: `productdevelopment.crutastic.com`.

## Brand and content rules

- Fonts: Sora 800 (headlines) and Inter 400/500/600 (body), from Google Fonts.
- Palette: Yellow `#FFD000`, Orange `#F08220`, Cyan `#00C3D8`, Turquoise `#007990`, Black `#1A1A1A`.
- Copy: casual, concise, commas instead of dashes. No em dashes anywhere. No religious imagery.
- Bright appears in the hero, Ask Bright, and Flashcards only. Not anywhere else.
- Manual and media links open in a new tab with `rel="noopener"`.
- Keep: no horizontal scroll at 360px, tap targets at least 44px, WCAG AA contrast, `prefers-reduced-motion` respected.

## Workflow

Edit index.html, commit, push to `main`, Pages rebuilds in 1 to 2 minutes. The Apps Script is deployed separately by Mark (see `_dev/apps-script/SETUP-ASK-BRIGHT.md`). The API key lives only in Apps Script Script Properties, never in this repo.

## Ask Bright's API key (Mark, 2026-11-07)

- The Apps Script lives in Mark's PERSONAL Google account (not Cru): script.google.com > Ask Bright > Project Settings > Script Properties > `ANTHROPIC_API_KEY`.
- Key comes from Mark's own Claude Console org ("Mark's Individual Org"): https://platform.claude.com/settings/keys
- Current key: "Ask Bright 2", made 2026-11-07, set to Never expire, workspace Default (the script sends no workspace header, so the key must be scoped to a workspace). Old 30-day key "Ask Bright" expired 2026-11-08.
- Mark's choice: Never-expiring keys for light apps like this. Claude can't create or paste keys; Mark does that, Claude tests by POSTing a question to ASK_URL.
- Not federation: Mark asked; it doesn't fit Apps Script or GitHub Pages sites.
- Later (Mark wants it): move the script to his Cru account. Means a new copy and new web app URL in ASK_URL; first check Cru's Google allows "Anyone" access to web apps.
- Planned: an "API keys" helper in ~/Projects/command-center listing every app's key, where it lives, and how to swap it.

## Two-Machine Rules

- Repos must live in a plain local folder, never inside a Google Drive-synced folder, because Drive can corrupt `.git` with conflict-copy files.
- Confirm the real local path on whichever machine you're on rather than assuming (currently `/Users/markmichal/Projects/pdf-framework-site`).
- Run `git pull` at the start of every session, on whichever machine you're on.
- Commit and push before stopping so the other machine can pick up current work.
- `.env` and `.claude/` must always be in `.gitignore` and must never be committed.
- Each machine needs `git config --global user.name` and `user.email` set to `Mark Michal` / `mark.michal@cru.org` so commits attribute correctly.

## Session Rhythm (automatic, every session)

**START of every session:**
1. Run `git pull`
2. Read `_dev/HANDOFF.md`
3. Summarize current state and open items in 2-3 sentences so Mark knows you're oriented

**END of every session:**
1. Update `_dev/HANDOFF.md` with a dated entry: what was built or decided, new parked items, state of open threads
2. Commit and push the update
3. Tell Mark "HANDOFF.md updated and pushed"

Do both without being asked. HANDOFF.md is the shared source of truth across two machines and between Claude Code and Claude chat.
