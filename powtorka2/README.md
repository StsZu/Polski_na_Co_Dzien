# Powtórka 2 — сторінки повторення (Polski krok po kroku 2, A2)

Те саме, що `powtorka/`, але для курсу 2 (A2). Дата-кероване, без build-step.

## Структура
```
powtorka2/
├── index.html          # список уроків (data/lessons.json)
├── lekcja.html         # ШАБЛОН: рендерить ?id=NN із data/lekcja-NN.json
├── data/
│   ├── lessons.json    # маніфест 23 уроків + прапор ready
│   └── lekcja-NN.json  # контент уроку
└── audio/LNN/          # ElevenLabs mp3 (Alex PL)
```

## Відмінності від powtorka A1
- Секція `gramatyka` — граматичні картки (таблиці + приклади).
- Тип `mono` у `czytanie` — монолог/текст (PL + переклад toggle + audio).
- Quiz: 3 опції + `fb` (пояснення-feedback) — формат Creator_quiz.

## Локально
`python3 -m http.server` у цій теці → `http://localhost:8000/`.

Статус: пілот — урок 01.
