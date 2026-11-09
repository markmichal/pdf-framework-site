# Product Development Framework site: notes for any AI helper

This file is for whatever AI is helping Mark (Claude today, maybe something else later). Read NOTES.md next (why it exists, decisions, history), then `_dev/HANDOFF.md` (the dated session log). README.md is the public front page on GitHub (where things live, how to update); keep it as it is. Copies of past conversations go in `chats/` (kept on this Mac only, never pushed).

One-page site for Cru Campus Ministry's Ministry Product Framework (formerly Product Development Framework), with "Ask Bright" (a chat box that answers from the framework docs) and flashcards. Live at https://mpf.crutastic.com. Mark is not a coder: plain words, no em dashes, clickable links.

## Rules
- Don't break the connections: `index.html` is everything (inline CSS and JS); `ASK_URL` at the top of its script points to the Ask Bright Apps Script (POST with `Content-Type: text/plain`, reply is `{answer}` or `{error}`); `flashcards.json` is fetched, so test through a local server; `_dev/` is skipped by GitHub Pages, so do NOT add `.nojekyll`.
- Brand: Sora 800 headlines, Inter body. Palette Yellow `#FFD000`, Orange `#F08220`, Cyan `#00C3D8`, Turquoise `#007990`, Black `#1A1A1A`. Casual, concise copy, commas instead of dashes, no em dashes, no religious imagery.
- Bright (the light bulb mascot) appears only in the hero, Ask Bright and Flashcards.
- Manual and media links open in a new tab with `rel="noopener"`. No horizontal scroll at 360px, tap targets 44px or more, WCAG AA contrast, respect `prefers-reduced-motion`.
- The API key lives only in Apps Script Script Properties, never in this repo. Claude can't create or paste keys; Mark does. Claude tests by POSTing `{"question": ...}` to `ASK_URL`. Key swap steps for every app: ~/Projects/command-center/API-KEYS.md.
- This repo is public, and pushing to `main` publishes the site. Keep private details out of every file.

## Two-machine rules
- The repo lives in a plain local folder, never inside a Google Drive synced folder (Drive can corrupt `.git`). Confirm the real path on whichever machine you're on (currently `/Users/markmichal/Projects/pdf-framework-site`).
- Run `git pull` at the start of every session.
- Commit and push before stopping so the other machine can pick up current work. (Mark's newer rule for all projects, 2026-11-09: never push without his OK. So ask him before the push.)
- `.env` and `.claude/` must always be in `.gitignore` and never committed.
- Each machine needs `git config --global user.name` and `user.email` set to Mark's name and Cru email.

## Session rhythm (automatic, every session)
Start, without being asked: `git pull`, read `_dev/HANDOFF.md`, then sum up the current state and open items in 2 to 3 sentences.

End, without being asked:
1. Update `_dev/HANDOFF.md` with a dated entry (what was built or decided, new parked items, state of open threads). Put lasting decisions in NOTES.md too.
2. Save a copy of the chat: `python3 ~/Projects/project-kit/save-chat.py ~/Projects/pdf-framework-site` (`chats/` is in .gitignore, so it stays on this Mac).
3. Make a save point: `git add -A && git commit -m "<what changed and why>"`, then push once Mark says OK. Tell Mark "HANDOFF.md updated" (and "pushed" if it was).
4. Back up: `~/Projects/project-kit/backup-projects.sh ~/Projects/pdf-framework-site` (copies only what the save point tracks).
