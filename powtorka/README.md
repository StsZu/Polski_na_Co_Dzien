# Powtórka — сторінки повторення (Polski krok po kroku 1, A1)

Дата-кероване повторення уроків. Студент читає й проходить quiz сам, викладач спостерігає.

## Структура

```
powtorka/
├── index.html          # список уроків (читає data/lessons.json)
├── lekcja.html         # ШАБЛОН: рендерить будь-який урок з ?id=NN
├── data/
│   ├── lessons.json    # маніфест 26 уроків + прапор ready
│   ├── lekcja-01.json  # контент уроку 01 (еталон схеми)
│   └── lekcja-NN.json  # наступні уроки
└── README.md
```

HTML один на всі уроки. Додати урок = додати `data/lekcja-NN.json` + `ready:true` у маніфесті.

## Запуск локально

`fetch` не працює через `file://`. Підніми сервер у цій теці:

```
python3 -m http.server 8000
```

Відкрий `http://localhost:8000/` (індекс) або `…/lekcja.html?id=01`.
На GitHub Pages працює без сервера.

## Додати наступний урок

Skill: `/build-lesson 02` — читає джерельні тексти (`lekcja_02.txt`, `L02.txt`, ID3 аудіо),
генерує `data/lekcja-02.json` за схемою уроку 01 → чернетка для перегляду викладачем.
Схема скіла: `.claude/skills/build-lesson/SKILL.md`.

## Схема lekcja-NN.json (коротко)

`id, title, goal` · `vocab[]` (групи карток) · `formulas[]` · `alfabet[]` (лише 01) ·
`czytanie[]` (блоки → діалоги/списки) · `zeszyt[]` · `manifests[]` · `mistakes[]` ·
`drills[]` · `quiz[]`. Будь-яку відсутню секцію просто не додавай — шаблон рендерить наявні.
