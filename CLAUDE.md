# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Pre-launch static educational site **«Polski na Co Dzień»** (Polish for everyday life). The goal is to clone the architecture of the sibling `../Aviation-quiz/` site — a no-build GitHub Pages site of quizzes, lessons, infographics, and songs — for Polish-language learning.

**Current state: raw materials only, no site wrapper yet.** There is no `index.html`, no `.gitignore`, no own git remote (the folder is tracked by the monorepo `Projects`). `plan-implemetation-polish.md` is the authoritative build plan and source of truth — read it in full before doing site work, and keep it in sync as steps complete. Its section 7 lists open decisions that must be settled with the user before launch (separate repo vs. git subtree; repo/slug name; single beige theme vs. keeping the Tailwind lesson as its own section; UI language).

## Current materials

- `draft/lekcja_26_MÓC_CHCIEĆ.md` — lesson source (Ukrainian) for MÓC & CHCIEĆ conditional/polite forms.
- `polish_class/26_m_c_chcie.html` + `draft/26_m_c_chcie.html` — the rendered lesson (Tailwind CDN, indigo theme). Two copies that **differ** — reconcile before publishing; don't assume they're identical.
- `quiz/quiz_MÓC_CHCIEĆ.md` — despite the `.md` extension, this already holds the finished **JSON array** of questions (`{title, question, options, correct, feedback}`), ready to drop into a quiz template. The quiz-generation step is effectively done.
- `img/Lekcja_gramatyki_MÓC_CHCIEĆ.png` — lesson infographic (no thumbnail generated yet).
- `audio/*.mp3` — two songs ("Chciałbym, Mogłabym — Grzeczne Słowa", "Chciałbym, Mogłabyś").
- `prompts/` — two content generators: `prompt_gemini_html.md` (lesson `.md` → single-file HTML) and `prompt_quiz_json.md` (lesson → 10-question JSON array in the exact contract above). `old/` is empty scratch.

## Target architecture (replicate from `../Aviation-quiz/`)

Every page is a **standalone HTML file with an inline `<style>` block** — no shared CSS, no JS framework, no bundler. Visual consistency is maintained by hand.

Shared beige theme to replicate on new pages: `font-family: Georgia`, background `#e7dfd2`, cards `#f8f3e9` with `1px solid #d4c7b3` borders and ~18–22px radius, text `#2f2822`, muted `#7a6858`; buttons/links use `"SF Pro Text", Arial, sans-serif`. Exception: the existing Tailwind lesson — its fate (convert to beige, or keep as a separate "immersive" section) is open decision 6.2.

Planned page types and their data-array contracts:

- **`index.html`** — menu: a `.quiz-list` grid of static `.quiz-card` `<article>`s, one per material. Adding a material = hand-adding a card here.
- **Quiz pages** (`quiz_*.html`) — driven by a JS `questions` array of `{title, question, options:[...], correct:<0-based index>, feedback}`; client-side scoring. Must include a `← Wszystkie quizy` back-link to `index.html`.
- **Gallery pages** — `infographics.html` (`images` array of `{file, title}`; full PNG in `img/`, ~200 KB JPEG preview in `img/thumb/` via `sips`) and `songs.html` (`songs` array; MP3 in `audio/`, cover+lyrics extracted from the MP3 itself). Content is added by editing the array, not the DOM.
- **Lessons** — either moved to root as `lekcja_*.html`, or kept in `polish_class/` as a themed section (then links to root pages need `../`).

## Content pipeline (after launch)

The user adds material by saying "додай `/path/to/file`". The flow: lesson `.md` (in `draft/`) → `prompts/prompt_gemini_html.md` → HTML; quiz source → `prompts/prompt_quiz_json.md` → JSON → quiz template. Then add a card to `index.html` + back-link, regenerate any thumbnail, and deploy.

`prompts/`, `draft/`, and the `.md` quiz sources are **generators, not published output** — they must be `.gitignore`d (along with `.DS_Store`, `.claude/`) when the repo is set up. Only finished HTML/img/audio gets published.

## Commands

No build/lint/test. Once pages exist, preview locally with `python3 -m http.server` from this folder and open `http://localhost:8000`. Deploy (post-launch) is `git push` → GitHub Pages, live in ~20–60s.

## Language

Docs and lesson content are Ukrainian (UI language for the site is open decision 4); Polish is the subject matter. Match the language of the file you're editing.
