# Polski na Co Dzień — інструкція з користування

Як публікувати матеріали на сайті **https://stszu.github.io/Polski_na_Co_Dzien/**.

## Що це

Статичний сайт на GitHub Pages для вивчення польської мови. Без збірки, без фреймворків — кожна сторінка самодостатня (inline CSS + vanilla JS). Містить:

- **Lekcja** — урок граматики `polish_class/26_m_c_chcie.html` (Tailwind CDN, власна тема). Лежить у підпапці `polish_class/`, тож його посилання на головну йде через `../index.html`.
- **Quiz** — інтерактивний квіз `quiz/polish-moc-chciec-quiz.html` (10 питань, миттєвий фідбек, підрахунок балів).
- **Infografiki** — галерея зображень `infographics.html` з прев'ю та переглядом на весь екран (lightbox).
- **Piosenki** — пісні `songs.html`: картки з обкладинками, плеєр і текст, що згортається.

Головна `index.html` — меню-дашборд: 4 картки матеріалів, hero з цілями, sidebar (трекер прогресу на чекбоксах, міні-дрил, таблиця типових помилок) і перемикач день/ніч.

## Ключові факти

- GitHub-репозиторій: `StsZu/Polski_na_Co_Dzien`, гілка `main`. Локальний клон: `Projects/Drafts/Polski_na_Co_Dzień/`.
- Жива адреса (відкривати тут): **https://stszu.github.io/Polski_na_Co_Dzien/**
  - `https://github.com/StsZu/Polski_na_Co_Dzien` — це код, а не сайт.
- Деплой автоматичний: після `git push` GitHub Pages оновлює сайт за ~20–60 секунд.
- Усі git-команди (`add`/`commit`/`push`) виконуються з папки сайту.
- Локальний перегляд без деплою: `python3 -m http.server` із папки сайту, відкрити `http://localhost:8000`.
- Тема єдина для всіх сторінок: беж (`#e7dfd2` фон, `#f8f3e9` картки, шрифт Georgia, акцент `#8d2930`). Темний режим зберігається в браузері (`localStorage['theme']`) і спільний для всіх сторінок.
- Інтерфейс — польською (`lang="pl"`).

## Дві ролі папок

- Публічне (йде в репо): `index.html`, `infographics.html`, `songs.html`, `polish_class/`, `quiz/`, `img/`, `img/thumb/`, `audio/`, `CLAUDE.md`, `RUN.md`.
- Приховане (`.gitignore`, не публікується): `prompts/` (генератори контенту), `old/`, `.claude/`, `.DS_Store`, `plan-implemetation-polish.md`.

`prompts/` — генератори: `prompt_gemini_html.md` (урок `.md` → HTML), `prompt_quiz_json.md` (текст → JSON-масив питань).

## Як додати матеріал (найпростіше)

Напиши Claude Code повідомлення з **шляхом до файлу** і словом «додай». Наприклад:

> додай урок з `/шлях/до/lekcja.md`

> додай інфографіку `/шлях/до/obrazek.png`

> додай пісню `/шлях/до/utwor.mp3`

Claude зробить решту автоматично (копіювання, картка, посилання, деплой, перевірку).

## Що відбувається під капотом (для довідки)

### Новий урок
1. Джерело `.md` прогнати через `prompts/prompt_gemini_html.md` → готовий HTML.
2. Файл покласти в `polish_class/` (як секцію) і додати **картку** `<article class="material-card">` в `index.html` (badge `badge-class`).
3. У сторінці уроку додати back-link на головну через `../index.html`.
4. `commit` + `push` + перевірка.

### Новий квіз
1. Джерело прогнати через `prompts/prompt_quiz_json.md` → JSON-масив `{title, question, options, correct, feedback}`.
2. JSON вкласти в шаблон квізу, файл покласти в `quiz/`.
3. Додати картку в `index.html` (badge `badge-quiz`), back-link `← Wszystkie materiały` у квізі.
4. `commit` + `push` + перевірка.

### Нова інфографіка (PNG)
1. Повний PNG → `img/`.
2. Стиснуте прев'ю (JPEG, ~200 КБ) → `img/thumb/` через `sips`:
   `sips -s format jpeg -s formatOptions 72 -Z 900 img/<file>.png --out img/thumb/<file>.jpg`
3. Запис у масив `images` у `infographics.html`: `{ file, title, links: [...] }` (`file` — ім'я без розширення).
4. `commit` + `push` + перевірка.

### Нова пісня (MP3 з Suno)
- Сторінку Suno **не можна** вставити iframe — пісні хостяться на сайті.
- MP3 із Suno самодостатній: усередині є **текст** (тег `lyrics-eng`) і **обкладинка**.
1. MP3 → `audio/`. **Перейменувати на ASCII-слаг** (без пробілів/діакритики/тире) — інакше URL ламається на Pages.
2. Витягти обкладинку → `img/<slug>.jpg`:
   `ffmpeg -i audio/<slug>.mp3 -an -vcodec copy img/<slug>.jpg`
3. Витягти текст: `ffprobe -v error -show_entries format_tags=lyrics-eng -of default=noprint_wrappers=1:nokey=1 audio/<slug>.mp3`
4. Додати запис у масив `songs` у `songs.html`: `{ file, title, artist, topic, links: [...], lyrics }`.
5. `commit` + `push` + перевірка.

## Структура файлів у репозиторії

```
index.html                # головна (меню-картки + dashboard)
infographics.html         # галерея інфографіки (масив images)
songs.html                # пісні (масив songs: плеєр + текст)
polish_class/             # уроки (Tailwind), back-link через ../
quiz/                     # інтерактивні квізи
img/                      # повні зображення + обкладинки пісень
img/thumb/                # прев'ю інфографіки (JPEG)
audio/                    # MP3 пісень (ASCII-слаги)
CLAUDE.md                 # правила для Claude Code
RUN.md                    # ця інструкція
```

## Якщо щось треба змінити вручну

- Картка на головній — статичний `<article class="material-card">` у `index.html` (порядок у розмітці = порядок на сторінці; не масив).
- Інфографіка — масив `images` у `infographics.html`.
- Пісня (назва/тема/текст) — масив `songs` у `songs.html`.

## Перевірка після деплою

Відкрити https://stszu.github.io/Polski_na_Co_Dzien/ і переконатися, що:
- нова картка з'явилась на головній;
- сторінка відкривається, посилання працюють (без 404);
- back-link `← Wszystkie materiały` повертає на головну;
- пісні грають, прев'ю інфографіки відкривається на весь екран.
