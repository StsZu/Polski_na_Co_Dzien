# AGENTS.md

This file provides guidance to Codex (Codex.ai/code) when working with code in this repository.

## What this is

Live static educational site **«Polski na Co Dzień»** (Polish for everyday life) for Polish-language learning. Architecture cloned from the sibling `../Aviation-quiz/`: a no-build GitHub Pages site of lessons, quizzes, infographics, and songs.

**Current state: live in production.**
- Live URL: <https://stszu.github.io/Polski_na_Co_Dzien/>
- Own git remote: `https://github.com/StsZu/Polski_na_Co_Dzien.git` (branch `main`). This folder also sits inside the monorepo `Projects`, but it is its own published repo.
- GitHub Pages: legacy source = branch `main`, path `/`. A root **`.nojekyll`** file disables Jekyll — the site is served as raw static files (no build step). Do not remove it; its absence caused recurring "Page build failed" emails.
- Deploy = `git push` → Pages rebuilds in ~20–60s.

`plan-implemetation-polish.md` (gitignored) was the original build plan — historical reference now that the site is launched.

## Site structure (what's published)

Root pages, each a **standalone HTML file with an inline `<style>` block** (no shared CSS, no framework, no bundler):

- `index.html` — home menu; a `.quiz-list` grid of static `.quiz-card` `<article>`s, one per section. Adding a section = hand-adding a card here.
- `quiz/polish-moc-chciec-quiz.html` — quiz page driven by a JS `questions` array of `{title, question, options:[...], correct:<0-based index>, feedback}`; client-side scoring. Has a back-link to `index.html`.
- `infographics.html` — gallery; `images` array of `{file, title}`. Full PNG in `img/`, ~200 KB JPEG preview in `img/thumb/` (via `sips`).
- `songs.html` — gallery; `songs` array. MP3 in `audio/`, cover + lyrics extracted from the MP3 itself.
- `polskie-idiomy.html` — 20 Polish idioms; audio from `audio/idiomy/idiomy-NN.mp3`, lyrics inline in a `TRACKS` array.
- `sluchanie.html` — listening exercises over `audio/krok_A1_aud_zeszyt_LNN.mp3` ("Krok po kroku A1").
- `polish_class/26_m_c_chcie.html` — the MÓC & CHCIEĆ lesson (Tailwind CDN, indigo theme — the one page that does **not** use the beige theme). Linked from `index.html` with the `polish_class/` prefix.

Data-driven section sub-sites (each is its own mini-app: a static `index.html` lesson list + a shared `lekcja.html` renderer that reads `?id=NN` and fetches `data/lekcja-NN.json`):

- `powtorka/` — **Powtórka A1**, 26+ lessons. `data/*.json` lesson manifests, `audio/`, `README.md`.
- `powtorka2/` — **Powtórka A2**, 23 lessons. Same pattern: `data/lekcja-01..23.json`, `audio/` (incl. `audio/song/` per-lesson songs), `SPEC-usny-trenazer.md`, `offer-gemini/` (alt single-file lesson HTML), `suno/` song sources.

Both are linked from `index.html` via `href="powtorka/"` and `href="powtorka2/"`.

## Beige theme (shared by all pages except the Tailwind lesson)

`font-family: Georgia`, background `#e7dfd2`, cards `#f8f3e9` with `1px solid #d4c7b3` borders and ~18–22px radius, text `#2f2822`, muted `#7a6858`; buttons/links use `"SF Pro Text", Arial, sans-serif`. Visual consistency is maintained by hand.

## Content pipeline

The user adds material by saying "додай `/path/to/file`". Flow: lesson `.md` → `prompts/prompt_gemini_html.md` → HTML; quiz source → `prompts/prompt_quiz_json.md` → 10-question JSON in the contract above → quiz template. For `powtorka*` sections, add a `data/lekcja-NN.json` and register it in that section's `index.html` lesson list. Then add/update a card in root `index.html`, regenerate any thumbnail, and `git push`.

`prompts/`, `old/`, `plan-implemetation-polish.md`, raw `Polskie idiomy/` source, and `powtorka2/suno/Songs/` originals are **generators/sources, not published output** — they are `.gitignore`d. Only finished HTML/img/audio gets published.

## Repo size note

All audio (`.mp3`) is committed directly to git: ~620 MB published content, ~750 MB `.git`. GitHub Pages soft limit is 1 GB, so there's headroom but the repo grows with each audio addition. Decision on record (2026-06): **keep one repo, do not split by topic** — the bytes are audio, not "too much site", and splitting would break the unified navigation/URL. Revisit only near the limit; the clean fix then is moving audio to a separate asset repo, not splitting the site.

## Commands

No build/lint/test. Preview locally with `python3 -m http.server` from this folder, open <http://localhost:8000>. Deploy = `git push` → GitHub Pages.

## Language

Docs and lesson content are Ukrainian; Polish is the subject matter; the site UI is Polish. Match the language of the file you're editing.
