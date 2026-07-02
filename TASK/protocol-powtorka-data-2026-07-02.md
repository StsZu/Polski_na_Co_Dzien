# Протокол перевірки: powtorka/data

Дата: 2026-07-02  
Завдання: `TASK/task-02-07-2026.md`  
Обсяг: 28 файлів у `powtorka/data/` (26 уроків `lekcja-*.json`, `lessons.json`, `sluchanie.json`).  
Блоки `mistakes` не оцінювалися як помилки контенту — лише перевірено коректність пояснень (див. розділ «Окремо»).

## Підсумок

| Показник | Значення |
|---|---|
| Файлів перевірено | 28 |
| Записів у протоколі | 36 |
| critical | 32 |
| medium | 4 |
| low | 0 |
| Виправлено в поточних файлах | 36 |
| Залишилось невиправленим | 0 |

Найчастіші типи: **punctuation** (звертання, коми перед `że`/`kiedy`/`to`) — 30 записів; **grammar** (узгодження, прийменники часу, відмінок) — 6 записів.

---

## Етап 1. Протокол помилок

Позначка **Статус**: `виправлено` — у поточній версії JSON текст уже змінений; `залишилось` — помилка досі в файлі.

### Усі записи (виправлено)

| № | ID | Урок | JSON-шлях | Оригінал (було) | Тип | Серйозність | Виправлення | Пояснення | Статус |
|---|---|---|---|---|---|---|---|---|---|
| 1 | 03 | Mami, kto to jest? | `czytanie[0].items[1].lines[0][1]` | `Cześć Mami. Co słychać?` | punctuation | critical | `Cześć, Mami. Co słychać?` | Звертання `Mami` виділяється комою. | виправлено |
| 2 | 04 | Jaki jesteś? | `czytanie[0].items[0].lines[0][1]` | `Cześć Javier.` | punctuation | critical | `Cześć, Javier.` | Ім'я у звертанні відокремлюється комою. | виправлено |
| 3 | 04 | Jaki jesteś? | `czytanie[0].items[0].lines[1][1]` | `Cześć Mami. Co słychać?` | punctuation | critical | `Cześć, Mami. Co słychać?` | Те саме правило звертання. | виправлено |
| 4 | 04 | Jaki jesteś? | `czytanie[0].items[1].lines[4][1]` | `No dobrze Mami, masz rację.` | punctuation | critical | `No dobrze, Mami, masz rację.` | Звертання всередині речення — з обох боків. | виправлено |
| 5 | 05 | Jesteś instruktorem tanga? | `czytanie[3].items[3].lines[0][1]` | `Cześć Mami! Co czytasz?` | punctuation | critical | `Cześć, Mami! Co czytasz?` | Кома після привітання перед іменем. | виправлено |
| 6 | 05 | Jesteś instruktorem tanga? | `czytanie[3].items[3].lines[1][1]` | `Cześć Javier! Czytam książkę biograficzną.` | punctuation | critical | `Cześć, Javier! Czytam książkę biograficzną.` | Те саме. | виправлено |
| 7 | 05 | Jesteś instruktorem tanga? | `czytanie[3].items[3].lines[7][1]` | `...tango, czy akordeon, to dla mnie...` | punctuation | medium | `...tango czy akordeon to dla mnie...` | У простому зіставленні коми перед одиничним `czy` і перед `to` зайві. | виправлено |
| 8 | 08 | Mami, jesteś głodna? | `czytanie[0].items[3].lines[8][1]` | `Brawo Mami. Wolę owocowy.` | punctuation | critical | `Brawo, Mami. Wolę owocowy.` | Звертання після вигуку `Brawo`. | виправлено |
| 9 | 09 | Lubisz marchewkę? | `czytanie[3].items[1].lines[0][1]` | `Cześć dziewczyny, co robicie?` | punctuation | critical | `Cześć, dziewczyny, co robicie?` | `dziewczyny` — звертання, кома з обох боків. | виправлено |
| 10 | 10 | Uwielbiam polskie jedzenie! | `czytanie[2].items[0].lines[4][1]` | `...jakiś dobry deser, albo chociaż...` | punctuation | medium | `...jakiś dobry deser albo chociaż...` | Перед одиничним `albo` у переліку кома не потрібна. | виправлено |
| 11 | 10 | Uwielbiam polskie jedzenie! | `czytanie[2].items[0].lines[5][1]` | `Oj Mami, nie złość się!` | punctuation | critical | `Oj, Mami, nie złość się!` | Вигук `Oj` і звертання `Mami` відокремлюються комами. | виправлено |
| 12 | 13 | Gdzie byłaś, Mami? Byłam w kinie | `title` | `Gdzie byłaś Mami? Byłam w kinie` | punctuation | critical | `Gdzie byłaś, Mami? Byłam w kinie` | Звертання в заголовку уроку. | виправлено |
| 13 | 13 | Gdzie byłaś, Mami? Byłam w kinie | `lessons.json` → `[12].title` | `Gdzie byłaś Mami? Byłam w kinie` | punctuation | critical | `Gdzie byłaś, Mami? Byłam w kinie` | Дубль заголовку в індексі. | виправлено |
| 14 | 13 | Gdzie byłaś, Mami? Byłam w kinie | `czytanie[0].items[0].lines[4][1]` | `Cześć Mami! Gdzie byłaś?` | punctuation | critical | `Cześć, Mami! Gdzie byłaś?` | Звертання після `Cześć`. | виправлено |
| 15 | 13 | Gdzie byłaś, Mami? Byłam w kinie | `czytanie[0].items[0].lines[5][1]` | `Cześć Shige! Byłam w...` | punctuation | critical | `Cześć, Shige! Byłam w...` | Те саме. | виправлено |
| 16 | 13 | Gdzie byłaś, Mami? Byłam w kinie | `czytanie[1].items[0].lines[1][1]` | `Cześć dziewczyny! Co słychać?` | punctuation | critical | `Cześć, dziewczyny! Co słychać?` | Групове звертання. | виправлено |
| 17 | 13 | Gdzie byłaś, Mami? Byłam w kinie | `czytanie[1].items[0].lines[2][1]` | `Cześć Uwe! Weekend był świetny!` | punctuation | critical | `Cześć, Uwe! Weekend był świetny!` | Те саме. | виправлено |
| 18 | 13 | Gdzie byłaś, Mami? Byłam w kinie | `czytanie[1].items[0].lines[8][1]` | `A ty Mami? Co robiłaś w weekend?` | punctuation | critical | `A ty, Mami? Co robiłaś w weekend?` | Звертання в короткому питанні. | виправлено |
| 19 | 15 | Karton czy pudełko? | `czytanie[0].items[2].lines[1][1]` | `Tak mamo?` | punctuation | critical | `Tak, mamo?` | Звертання `mamo`. | виправлено |
| 20 | 15 | Karton czy pudełko? | `czytanie[1].items[0].lines[0][1]` | `Cześć Sylwia! Jedziesz z nami...` | punctuation | critical | `Cześć, Sylwia! Jedziesz z nami...` | Ім'я у звертанні. | виправлено |
| 21 | 15 | Karton czy pudełko? | `czytanie[4].items[1].lines[0][1]` | `Cześć Javier, dzwoniłeś do mnie.` | punctuation | critical | `Cześć, Javier, dzwoniłeś do mnie.` | Звертання всередині речення — з обох боків. | виправлено |
| 22 | 19 | Wszędzie dobrze, ale w domu najlepiej | `czytanie[1].items[0].lines[2][1]` | `Pamiętaj żeby było... bo jeśli będzie elektryczne to zimą...` | punctuation | critical | `Pamiętaj, żeby było... bo jeśli będzie elektryczne, to zimą...` | Кома перед `żeby`; у `jeśli..., to...` — кома перед `to`. | виправлено |
| 23 | 22 | Dokąd pojedziemy na weekend? | `czytanie[1].items[4].lines[3][1]` | `Ciekawe tylko kiedy. Wyślemy im SMS-a...` | punctuation | medium | `Ciekawe tylko, kiedy. Wyślemy im SMS-a...` | `kiedy` вводить підрядну частину. | виправлено |
| 24 | 22 | Dokąd pojedziemy na weekend? | `czytanie[3].items[0].lines[0][1]` | `Cześć Javier.` | punctuation | critical | `Cześć, Javier.` | Звертання. | виправлено |
| 25 | 22 | Dokąd pojedziemy na weekend? | `czytanie[3].items[0].lines[1][1]` | `O, cześć dziewczyny. Zaraz przedstawię...` | punctuation | critical | `O, cześć, dziewczyny. Zaraz przedstawię...` | `dziewczyny` — звертання. | виправлено |
| 26 | 23 | Za małe? Za duże? W sam raz! | `czytanie[1].items[3].lines[5][1]` | `...o rozmiar większe? Te są za małe.` | grammar | critical | `...o rozmiar większy? Te są za małe.` | `rozmiar` — чол. рід; прикметник `większy`. | виправлено |
| 27 | 23 | Za małe? Za duże? W sam raz! | `drills[2][1]` | `Czy mogę prosić o rozmiar większe?` | grammar | critical | `Czy mogę prosić o rozmiar większy?` | Те саме узгодження. | виправлено |
| 28 | 25 | Ani ręką, ani nogą... | `czytanie[1].items[2].lines[1][1]` | `Cześć Angela. Co z tobą?` | punctuation | critical | `Cześć, Angela. Co z tobą?` | Звертання. | виправлено |
| 29 | 25 | Ani ręką, ani nogą... | `czytanie[2].items[0].lines[5][1]` | `Niedobrze mi kiedy myślę o jedzeniu.` | punctuation | critical | `Niedobrze mi, kiedy myślę o jedzeniu.` | Кома перед підрядною частиною з `kiedy`. | виправлено |
| 30 | 25 | Ani ręką, ani nogą... | `czytanie[3].items[1].lines[0][1]` | `Dzień dobry pani doktor.` | punctuation | critical | `Dzień dobry, pani doktor.` | Звертання `pani doktor`. | виправлено |
| 31 | 25 | Ani ręką, ani nogą... | `czytanie[4].items[0].lines[5][1]` | `Nie, Angela jest obcokrajowką. Nie mówi po polsku.` | grammar | medium | `Nie, Angela jest cudzoziemką. Nie mówi po polsku.` | `obcokrajowką` — нестандартна форма; для «іноземка» природніше `cudzoziemką`. | виправлено |
| 32 | 26 | Same problemy! | `czytanie[0].items[2].lines[0][1]` | `Cześć Mami. Co tam masz?` | punctuation | critical | `Cześć, Mami. Co tam masz?` | Звертання. | виправлено |
| 33 | 26 | Same problemy! | `czytanie[2].items[0].lines[1][1]` | `Cześć Aniu. Nie dojadę na czas...` | punctuation | critical | `Cześć, Aniu. Nie dojadę na czas...` | Звертання у відмінку кличного (`Aniu`). | виправлено |
| 34 | 12 | Co robisz w poniedziałek o ósmej? | `czytanie[0].items[2].lines[1][1]` | `Dzień dobry panu. Co słychać?` | punctuation | critical | `Dzień dobry, panu. Co słychać?` | Звертання `panu` (форма grzecznościowa) відокремлюється комою. У тому ж діалозі сусід уже каже `Dzień dobry, pani Ewo.` — потрібна узгодженість. | виправлено |
| 35 | 14 | Z przewodnikiem po Krakowie | `czytanie[1].items[1].lines[0][1]` | `Dzień dobry państwu. Nazywam się Jan Krall...` | punctuation | critical | `Dzień dobry, państwu. Nazywam się Jan Krall...` | Звертання `państwu` виділяється комою. | виправлено |
| 36 | 25 | Ani ręką, ani nogą... | `czytanie[3].items[0].lines[6][1]` | `Mam wolny termin na jutro rano na 7.30. do doktor Kowalik. Pasuje panu?` | grammar / punctuation | medium | `Mam wolny termin na jutro rano o 7:30 u lekarki Kowalik. Pasuje panu?` | 1) Година — `o 7:30`, не `na 7.30`. 2) Місцевий після `u`: `u lekarki Kowalik`, не `do doktor Kowalik`. 3) Крапка після `7.30` розбивала речення штучно. | виправлено |

---

## Етап 2. Внесені виправлення

Усі 36 фрагментів з протоколу виправлено:

- `lekcja-03.json`: 1 правка.
- `lekcja-04.json`: 3 правки.
- `lekcja-05.json`: 3 правки.
- `lekcja-08.json`: 1 правка.
- `lekcja-09.json`: 1 правка.
- `lekcja-10.json`: 2 правки.
- `lekcja-12.json`: 1 правка (№ 34).
- `lekcja-13.json`: 6 правок.
- `lekcja-14.json`: 1 правка (№ 35).
- `lekcja-15.json`: 3 правки.
- `lekcja-19.json`: 1 правка.
- `lekcja-22.json`: 3 правки.
- `lekcja-23.json`: 2 правки.
- `lekcja-25.json`: 5 правок (№ 28–31, 36).
- `lekcja-26.json`: 2 правки.
- `lessons.json`: 1 правка.

Останні три правки (2026-07-02):

```diff
# lekcja-12.json
- Dzień dobry panu. Co słychać?
+ Dzień dobry, panu. Co słychać?

# lekcja-14.json
- Dzień dobry państwu. Nazywam się Jan Krall, jestem przewodnikiem po Krakowie.
+ Dzień dobry, państwu. Nazywam się Jan Krall, jestem przewodnikiem po Krakowie.

# lekcja-25.json
- Mam wolny termin na jutro rano na 7.30. do doktor Kowalik. Pasuje panu?
+ Mam wolny termin na jutro rano o 7:30 u lekarki Kowalik. Pasuje panu?
```

---

## Окремо: блоки `mistakes`

Перевірено всі 26 уроків із блоком `mistakes`. Пари «неправильно → правильно» коректні; пояснення українською відповідають навчальній меті. Приклади:

- `Mami jest smutny` → `Mami jest smutna` (узгодження роду)
- `Jestem z Japonia` → `Jestem z Japonii` (родовий після `z`)
- `Mieszkam w Kraków` → `Mieszkam w Krakowie` (місцевий після `w`)
- `Mówię po polski` → `Mówię po polsku` (конструкція `mówić po + -ku`)

Випадків, де «помилка» і «виправлення» збігаються, не знайдено.

## Навмисно не позначено як помилку

| Урок | Місце | Фрагмент | Чому |
|---|---|---|---|
| 08 | `czytanie[0].items[3].lines[6][1]` | `Malinaowy` | У наступній репліці тато виправляє на `Malinowy` — навчальний приклад помилки учня, не дефект JSON. |

## Перевірка після правок

- Усі 28 JSON-файлів у `powtorka/data/` коректно парсяться (`JSON.parse`).
- Старі помилкові фрагменти з таблиці № 1–36 не знайдені.
- Конструкції `mówić po polsku / po japońsku` у діалогах і вправах — без `w polsku` / `na polsku`.
- Узгодження `smutna` / `smutny` у діалогах про Mami — коректне.

## Рекомендація

**Виправлено:** усі 36 записів протоколу.

**Можна залишити:** `Malinaowy` у L08 як навчальний приклад.

**Перевірити з викладачем / підручником:** чи потрібно синхронізувати аналогічні звертання в `sluchanie.json` (транскрипти аудіо) — там окремі правила, бо це дослівні тексти з диска, а не відредаговані діалоги уроків.