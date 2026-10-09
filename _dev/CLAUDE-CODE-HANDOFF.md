# Claude Code handoff: Product Development Framework site

Paste everything below the line into Claude Code, opened in the new repo folder, after you copy this handoff folder's contents into the repo.

---

We're building the intro website for Cru Campus Ministry's **Product Development Framework**. It's a one page, static site hosted on GitHub Pages, the same setup as my Legacy site (highschoollegacy.crutastic.com). The design is approved. Your job is to turn the mockup into a clean, production site that works great on desktop and phones.

## What's in this folder

- `design-reference/SiteV1-OnePage.dc.html`: the approved desktop mockup. It's HTML inside a design tool wrapper: the `<helmet>` block holds the CSS, the content sits inside `<x-dc>`, and the `<script type="text/x-dc">` at the bottom is tool metadata (ignore it). Match this design closely: colors, fonts, spacing, section order, copy, and links.
- `assets/mascot/*.webp`: Bright, the light bulb mascot (22 poses, transparent backgrounds). The site uses `welcome-a`, `thinking-b`, and `thumbsup-b`. Use `icon.webp` for the favicon and share image.
- `assets/framework/*.webp`: the six stage circles (`bright-immerse` ... `bright-monitor`) and three role icons.
- `flashcards.json`: 20 flashcards for the flashcard section.
- `apps-script/ask-bright.gs`: the backend for the "Ask Bright" box (I deploy this myself in Google Apps Script; you just call it).
- I'll add the Cru brandmark at `assets/brand/cru-brandmark.svg`. Use it in the nav where the mockup has the placeholder. If it isn't there yet, leave a clearly marked TODO.

## Build

1. A single `index.html` with inline CSS and JS (no framework, no build step), plus the `assets/` folder. Move `design-reference/`, `apps-script/`, and this handoff file into a `_dev/` folder so they stay in the repo but aren't published (GitHub Pages skips underscore folders by default; don't add `.nojekyll`).
2. Copy the mockup's section order exactly: sticky nav, hero, Why it matters, Framework at a glance with Roles (one boxed unit), Ask Bright, Learn it your way, Toolbox, Flashcards, footer.
3. **Responsive** (desktop first, phone friendly):
   - Nav collapses to a menu button under about 900px. Keep "Open the manual" visible.
   - Hero stacks: text first, Bright below and smaller.
   - Framework: 6 circles in a row on desktop; 3 per row on tablet (Design row, Deliver row, with their cycle labels above each row); 2 per row on phone. Hide the wavy ribbon below desktop. The split yellow/teal background should follow the rows when stacked (yellow behind Design, teal behind Deliver).
   - Roles, Why cards, Learn cards, and Toolbox go to 1 or 2 columns as space allows.
   - No horizontal scrolling at 360px wide. All tap targets at least 44px.
4. **Ask Bright** box:
   - `const ASK_URL = 'PASTE_APPS_SCRIPT_URL_HERE';` at the top of the script.
   - POST with `fetch(ASK_URL, {method:'POST', headers:{'Content-Type':'text/plain;charset=utf-8'}, body: JSON.stringify({question})})`. Text/plain avoids a CORS preflight, which Apps Script can't answer. Response is `{answer}` or `{error}`.
   - Show a friendly loading state ("Bright is thinking..."), swap the mascot to `thinking-a` while waiting and back after.
   - Render the answer safely: escape HTML, then turn blank lines into paragraphs and lines starting with "- " into a bulleted list. Nothing else.
   - The three chips fill the input and submit. Enter submits. Limit input to 600 characters.
   - If ASK_URL isn't set yet, show "Ask Bright is almost ready" instead of erroring.
5. **Flashcards**: load from `flashcards.json` (or inline it). Previous, Flip, Next, a "3 of 20" counter, a Shuffle button, keyboard support (arrows, space to flip). Flip should be a quick CSS flip that respects reduced motion.
6. **Toolbox**: replace the mockup's six cards with these six real tools (all open in a new tab):
   - The full manual: https://docs.google.com/document/d/1kyz9enZlTFBPRYRPc9nos777XmljZIhIUsn060okeJ4/edit
   - Project worksheet ("Track progress, decisions, and roles through each stage."): https://docs.google.com/document/d/1G_YdHbFibjBcJWg5EhX-euiW_Ocb8VjBXJpyOJbrDVo/template/preview
   - Product story deck ("Share your project's who, what, why, how, and when."): https://docs.google.com/presentation/d/1tL5zPvExHKZWVOGZAA6g3thDW7agfzNYdWbudocxYQM/edit?usp=sharing
   - Project charter ("Name the problem, the people, and what success looks like."): https://docs.google.com/document/d/1G0Phq3WC_g036b2YtDZnSjXBQQZfvmG3gA5QuNTZxm0/template/preview
   - Empathy map ("See through your audience's eyes during Immerse."): https://drive.google.com/file/d/1hbucyDjGHyRjwS0n5PdZwBn2Sdtn3212/view?usp=sharing
   - Persona template ("Turn what you learned into people you design for."): https://docs.google.com/presentation/d/1AGc1seQJkkU1zyrV8VqQQg_U7G1qEDmg07axoeuUrrI/edit?usp=sharing
   Remove the "Idea" tags.
7. **Motion and accessibility**: keep Bright's gentle float, turn it off with `prefers-reduced-motion`. Images that are decorative get `alt=""`; Bright images get a short `role="img"` label. WCAG AA contrast. Visible focus styles. Proper heading order. Skip link to main content.
8. **Head**: title "Product Development Framework | Cru Campus Ministry", meta description, Open Graph tags using `assets/mascot/icon.webp`, favicon from the same image. Load Sora 800 and Inter 400/500/600 from Google Fonts.
9. **Hosting**: GitHub Pages from `main`. Add a `CNAME` file with `framework.crutastic.com` (I'll confirm the subdomain and add the DNS record).
10. Add a short `README.md` (what the site is, where content lives, how to update Ask Bright's URL) and a `CLAUDE.md` with project notes, following the same Two Machine Rules and Session Rhythm I use on the Legacy site.

## Content rules

- All manual and media links open in a new tab with `rel="noopener"`.
- Copy style: casual, concise, commas instead of dashes. No em dashes anywhere.
- No religious imagery.
- Bright appears in the hero, Ask Bright, and Flashcards only. Don't add him elsewhere.

When done, run it locally, check 360px, 768px, and 1280px widths, fix anything that breaks, then commit and push. Tell me the steps left for me (DNS, Pages settings, ASK_URL).
