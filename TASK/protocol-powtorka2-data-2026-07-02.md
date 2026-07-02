# Протокол перевірки: powtorka2/data

Дата: 2026-07-02  
Завдання: `TASK/task-02-07-2026-2.md`  
Обсяг: 24 файли у `powtorka2/data/` (23 уроки `lekcja-*.json` + `lessons.json`).  
JSON-файли **змінено** (28 critical Блоку B + 28 Блоку A); протокол оновлено 2026-07-02.

## Короткий підсумок

| Показник | Значення |
|---|---|
| Файлів перевірено | 24 |
| Записів у протоколі | 67 |
| critical (усього / залишилось) | 48 / 0 |
| medium (усього / залишилось) | 18 / 10 |
| low (усього / залишилось) | 4 / 1 |
| Виправлено (Блок A + critical Блоку B) | 56 |
| Залишилось невиправленим | 11 (10 medium, 1 low) |

Найчастіші типи помилок: **translation-mismatch** (14), **punctuation** (12), **grammar / agreement / case-government** (11), **spelling** (9), **factual-inconsistency** (8), **syntax** (5), **teaching-rule-issue** (2).

Особлива перевірка уроків **01–04**: таблиці `gramatyka`, `quiz` і `drills` загалом коректні; критичні проблеми — у `czytanie`, перекладах діалогів і розбіжностях між секціями (L03).

---

## Етап 1. Протокол помилок

Позначка **Статус**: `виправлено` — текст уже змінений у JSON; `залишилось` — помилка досі в файлі.  
Колонка **JSON**: `yes` — потрібна правка в JSON; `no` — лише переклад/пояснення.

### Блок A. Раніше виправлені записи (28) — статус OK

| № | ID | Урок | JSON-шлях | Тип блоку | Було → стало (скорочено) | Тип | Серйозність | Статус |
|---|---|---|---|---|---|---|---|---|
| 1 | 02 | Dopełniacz jest wszędzie | `song.lyrics` | song | `siedemdziesiątym siódmym` → `dziewięćdziesiątym siódmym` | factual-inconsistency | critical | виправлено |
| 2 | 02 | Dopełniacz jest wszędzie | `song.lyrics` | song | `zniszczyła domów…` → `zniszczyła domy, szkoły i drogi…` | case-government | critical | виправлено |
| 3 | 02 | Dopełniacz jest wszędzie | `song.lyrics` | song | `pięć i pięćdziesiąt osób` → `pięćdziesiąt sześć osób` | factual-inconsistency | critical | виправлено |
| 4 | 02 | Dopełniacz jest wszędzie | `song.lyrics` | song | `Siedem tysięcy` → `Ponad siedem tysięcy osób` | factual-inconsistency | medium | виправлено |
| 5 | 07 | Praca | `gramatyka[2].words` | gramatyka | `Cześć Stary!` → `Cześć, stary!` | punctuation | medium | виправлено |
| 6 | 07 | Praca | `song.lyrics` | song | `Cześć, Stary!` → `Cześć, stary!` | spelling | medium | виправлено |
| 7 | 16 | Przygody | `czytanie[0].items[1].text` | czytanie | `o wypadek nie trudno` → `o wypadek nietrudno` | spelling | critical | виправлено |
| 8 | 16 | Przygody | `czytanie[0].items[1].text` | czytanie | `Nie wiadomo skąd` → `Nie wiadomo, skąd` | punctuation | medium | виправлено |
| 9 | 16 | Przygody | `czytanie[0].items[1].tr` | translation | `Невідомо звідки` → `Невідомо, звідки` | punctuation | medium | виправлено |
| 10 | 16 | Przygody | `czytanie[0].items[1].text` | czytanie | `nie wiedziałem co` → `nie wiedziałem, co` | punctuation | critical | виправлено |
| 11 | 16 | Przygody | `song.lyrics` | song | `wszystko dobre!` → `wszystko dobrze!` | word-choice | critical | виправлено |
| 12 | 16 | Przygody | `song.lyrics` | song | `zacisnij` → `zaciśnij` | spelling | critical | виправлено |
| 13 | 19 | Zielono mi! | `czytanie[1].items[0].text` | czytanie | `dopóźna` → `do późna` | spelling | critical | виправлено |
| 14 | 19 | Zielono mi! | `czytanie[1].items[0].tr` | translation | `в фірмі` → `у фірмі` | style/naturalness | low | виправлено |
| 15 | 19 | Zielono mi! | `czytanie[1].items[0].text` | czytanie | `mieszkałem` → `mieszkałam` | agreement | critical | виправлено |
| 16 | 19 | Zielono mi! | `czytanie[1].items[0].text` | czytanie | `nie mogłem` → `nie mogłam` | agreement | critical | виправлено |
| 17 | 19 | Zielono mi! | `czytanie[1].items[0].tr` | translation | `жив` / `міг` → `жила` / `могла` | translation-mismatch | critical | виправлено |
| 18 | 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `gdyby niewielki wybór` → `gdyby nie duży wybór` | syntax | critical | виправлено |
| 19 | 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `a jak ognia, boi się` → `a internetu… boi się jak ognia` | syntax | critical | виправлено |
| 20 | 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `W najważniejsze sprzęty…` → `Swoje mieszkanie… w najważniejsze sprzęty` | syntax | medium | виправлено |
| 21 | 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `Kupując jedzenie szuka` → `Kupując jedzenie, szuka` | punctuation | critical | виправлено |
| 22 | 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `nie wie dokładnie co` → `nie wie dokładnie, co` | punctuation | critical | виправлено |
| 23 | 20 | Rysopis Polaka konsumenta | `zeszyt[0].text` | zeszyt | `64-te urodziny` → `64. urodziny` | spelling | critical | виправлено |
| 24 | 20 | Rysopis Polaka konsumenta | `zeszyt[1].text` | zeszyt | `Zainteresowaniem czytają` → `Z zainteresowaniem czytają` | case-government | critical | виправлено |
| 25 | 20 | Rysopis Polaka konsumenta | `zeszyt[1].text` | zeszyt | `po czym, omijając` (коми) | punctuation | medium | виправлено |
| 26 | 21 | Sztuka | `czytanie[4].items[1].text` | czytanie | `że, korzystając…, popełniają` (коми) | punctuation | critical | виправлено |
| 27 | 23 | Czas na egzamin! | `czytanie[1].items[0].text` | czytanie | `że, będąc wzrokowcem, powinnam` (коми) | punctuation | critical | виправлено |
| 28 | 23 | Czas na egzamin! | `zeszyt[0].tr` п. 18 | translation | `Конфліктів не уникнути` (UA виправлено) | translation-mismatch | critical | виправлено (лише UA) |

---

### Блок B. Нові знахідки (39)

**Critical (№30–31, 35–40, 42–43, 45–52, 54–56, 57–61, 65–67) — виправлено 2026-07-02.**  
**Залишилось:** №29, 32–34, 41, 44, 53, 60, 62–64 (medium/low).

| № | ID | Урок | JSON-шлях | Тип блоку | Оригінал | Тип помилки | Серйозність | Виправлення | Пояснення (UA) | JSON | Статус |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 29 | 03 | Teatr | `title` | title | `Teatr` | factual-inconsistency | medium | `Kino` / `W kinie` | Увесь контент уроку — кіно, каса, `do kina` / `na film`; заголовок вводить в оману. | yes | залишилось |
| 30 | 03 | Teatr | `czytanie[1].items[0].text` | czytanie | `Vita Corleone` | spelling | critical | `Vito Corleone` | Правильне ім'я героя «Хрещеного батька» — *Vito*. UA-переклад уже має «Віто». | yes | виправлено |
| 31 | 03 | Teatr | `czytanie[0].items[0].lines[3][2]` | czytanie | `Трохи задалеко близько` | translation-mismatch | critical | `Трохи занадто близько` | PL: `Trochę za blisko` = «занадто близько»; UA суперечливий. | no | виправлено |
| 32 | 03 | Teatr | `zeszyt[4].lines[5][1]` | zeszyt | `Niestety nie są, tylko z brzegu.` | grammar | medium | `Niestety są tylko z brzegu.` / `…nie ma miejsc w środku, tylko z brzegu.` | На питання про місця в середині: місця **є**, але лише крайові; `nie są` суперечить `tylko z brzegu`. | yes | залишилось |
| 33 | 02 | Dopełniacz jest wszędzie | `czytanie[1].items[0].lines[3][2]` | czytanie | `Анджело, а ти пам’ятаєш…` | translation-mismatch | medium | `Анджела, а ти пам’ятаєш…` | *Angela* — жіноче ім'я; «Анджело» — чоловіча форма звертання. | no | залишилось |
| 34 | 06 | Edukacja | `gramatyka[2].table.rows[4][2]` | gramatyka | `Говорити польською важко.` | translation-mismatch | medium | `Мовлення польською важке.` | PL: іменник `mówienie` (сер. рід), не інфінітив; переклад губить граматичну модель. | no | залишилось |
| 35 | 07 | Praca | `zeszyt[0].title` vs `zeszyt[0].text` | zeszyt | `Jolanta` / `Joanna Łapińska` | factual-inconsistency | critical | Узгоднити на `Joanna` | Різні імена в заголовку й тексті одного zeszyt. | yes | виправлено |
| 36 | 07 | Praca | `czytanie[1].items[2].text` | czytanie | `Znam trochę język niemiecki` | case-government | critical | `Znam trochę języka niemieckiego` | Після `trochę` — родовий: *języka niemieckiego*. | yes | виправлено |
| 37 | 07 | Praca | `zeszyt[0].text` | zeszyt | `Znam trochę język angielski` | case-government | critical | `Znam trochę języka angielskiego` | Та сама помилка керування відмінком. | yes | виправлено |
| 38 | 08 | Ja swoje wiem! | `czytanie[1].items[0].tr` | czytanie | `нахилитися по неї` | translation-mismatch | critical | `нахилитися по нього` | PL: `po niego` (для *długopis*, чол. р.); UA змінює рід. | no | виправлено |
| 39 | 09 | Nie zapomnij paszportu! | `czytanie[2].items[0].lines[5][2]` | czytanie | `платитимемо за перевагу` | translation-mismatch | critical | `платитимемо за надлишковий багаж` | `nadbagaż` ≠ `перевага`; повна втрата змісту в аеропорті. | no | виправлено |
| 40 | 10 | Kocham Cię, Polsko! | `czytanie[3].items[0].lines[6][2]` | czytanie | `мене не відмовиш` | translation-mismatch | critical | `мене не відраїш` / `не знеохотиш` | `zniechęcić` = розхолодити, відбити охоту; не «відмовиш». | no | виправлено |
| 41 | 11 | Wchodzisz czy wychodzisz? | `czytanie[1].items[0].lines[10][2]` | czytanie | `Підходи, тобто ігри…` | translation-mismatch | medium | `Польові ігри` / `ігри на місцевості` | `podchody` (gry terenowe) ≠ «підходи». | no | залишилось |
| 42 | 12 | W jeździe | `czytanie[2].items[0].lines[1][2]` | czytanie | `просто, як двічі по два` | translation-mismatch | critical | `просто, як бік стільця` / `як дріт` | Ідіома `proste jak drut` ≠ арифметичне «двічі два». | no | виправлено |
| 43 | 12 | W jeździe | `czytanie[1].items[0].text` | czytanie | `oferty domek na weekend` | case-government | critical | `oferty domku na weekend` | Після `oferty` (р. від.) — *domku*. | yes | виправлено |
| 44 | 12 | W jeździe | `czytanie[1].items[0].text` | czytanie | `mapa… od Państwa była` | punctuation | low | `…od Państwa**,** była` | Кома перед підрядним `była`. | yes | залишилось |
| 45 | 13 | Komu — życie to nie bajka | `zeszyt[0].lines[7][1]` | zeszyt | `A myślałeś kiedyś o wolontariacie?` | agreement | critical | `A myślałaś kiedyś o wolontariacie?` | Javier звертається до Mami (жін.); у `czytanie` уже `myślałaś`. | yes | виправлено |
| 46 | 15 | Wesołych Świąt! | `czytanie[0].items[0].text` | czytanie | `11 listopada 1918 roku to oficjalny I wojny światowej` | grammar | critical | `…to oficjalny koniec I wojny światowej` | Бракує іменника `koniec`; UA-переклад уже має «офіційний кінець». | yes | виправлено |
| 47 | 15 | Wesołych Świąt! | `czytanie[1].items[0].text` | czytanie | `a u żółwka Matka Święta` | spelling | critical | `a u żłóbka Matka Święta` | `żółwka` = черепаха; у колядці — `żłóbka` (ясли). | yes | виправлено |
| 48 | 15 | Wesołych Świąt! | `czytanie[1].items[0].text` | czytanie | `pastuszkowie do swych trzut biegną` | spelling | critical | `…do swych trzód biegną` | Артефакт транскрипції Whisper: `trzut` → `trzód`. | yes | виправлено |
| 49 | 15 | Wesołych Świąt! | `czytanie[1].items[0].text` | czytanie | `wetlejem Dziecina Święta` | spelling | critical | `w żłóbku Dziecina Święta` | `wetlejem` → `w żłóbku`. | yes | виправлено |
| 50 | 15 | Wesołych Świąt! | `czytanie[1].items[0].text` | czytanie | `wznosi w górę Sferą Częta` | spelling | critical | `wznosi w górę rączęta` | `Sferą Częta` → `rączęta` (рученята). | yes | виправлено |
| 51 | 15 | Wesołych Świąt! | `drills[8][1]` | drills | `Wzięła opłatek i zaczęła się dzielić.` | grammar | critical | `…zaczęła go dzielić.` | Ділять **облатку** → `go`, не голосове `się dzielić`. У пісні Zwrotka 2: `dzieli się nim`. | yes | виправлено |
| 52 | 15 | Wesołych Świąt! | `song.lyrics` | song | `Wzięła opłatek, zaczęła się dzielić` | grammar | critical | `…zaczęła go dzielić` | Та сама помилка, що в drills. | yes | виправлено |
| 53 | 16 | Przygody | `goal` | goal | `…опис пригод і situacji ·…` | translation-mismatch | medium | `…опис пригод і ситуацій ·…` | Польське `situacji` лишилось у українському `goal`. | yes | залишилось |
| 54 | 16 | Przygody | `vocab[0].items[9][1]` | vocab | `сироти / мурашки по шкірі` | translation-mismatch | critical | `мурашки по шкірі` | `сироти` = сироти; `gęsia skórka` — лише «мурашки». | yes | виправлено |
| 55 | 16 | Przygody | `czytanie[0].items[1].text` | czytanie | `jesień była wyjątkowo piękna` | agreement | critical | `jesień był wyjątkowo piękny` | `jesień` — чол. рід. | yes | виправлено |
| 56 | 18 | Królestwo zwierząt | `czytanie[0].items[0].lines[9–11]` | czytanie | Speaker: Angela → `Urodziłam się 4 kwietnia… barana` | factual-inconsistency | critical | Розділити репліки: Angela «To też nie jest wesołe» + Mami з гороскопом Baran | Angela раніше каже 8.03 (Риби); тут 4.04 (Овен). Quiz про Mami посилається на цей рядок. | yes | виправлено |
| 57 | 20 | Rysopis Polaka konsumenta | `czytanie[3].items[0].lines[1][1]` | czytanie | `Dzień dobry panu.` | punctuation | critical | `Dzień dobry, panu.` | Звертання відокремлюється комою. | yes | виправлено |
| 58 | 20 | Rysopis Polaka konsumenta | `czytanie[3].items[1].lines[0][1]` | czytanie | `Dzień dobry panu, panie Górecki.` | punctuation | critical | `Dzień dobry, panu, panie Górecki.` | Кома після `Dzień dobry`. | yes | виправлено |
| 59 | 20 | Rysopis Polaka konsumenta | `czytanie[3].items[1].lines[1][1]` | czytanie | `Dzień dobry pani.` | punctuation | critical | `Dzień dobry, pani.` | Те саме правило звертання. | yes | виправлено |
| 60 | 20 | Rysopis Polaka konsumenta | `zeszyt[3].text` | zeszyt | `Co za czasy proszę pani, dawniej…` | punctuation | medium | `Co za czasy, proszę pani, dawniej…` | Вставне `proszę pani` береться в коми. | yes | залишилось |
| 61 | 20 | Rysopis Polaka konsumenta | `zeszyt[3].text` | zeszyt | `a starą przynosi mnie z pytaniem` | case-government | critical | `a starą przynosi mi z pytaniem` | `przynosić` + давальний `mi`; UA уже «приносить мені». | yes | виправлено |
| 62 | 20 | Rysopis Polaka konsumenta | `czytanie[4].items[0].lines[1][1]` | czytanie | `w zebrze, uryłki i tak dalej` | spelling | medium | `w zebrze, Ryłko i tak dalej` | `uryłki` — помилка бренду *Ryłko*. | yes | залишилось |
| 63 | 22 | Muzeum? | `czytanie[4].block` | czytanie | `Wywiad z Hannele Tilles` | factual-inconsistency | medium | `Wywiad z Hannele Tyles` | У тексті B1: `Hannele Tyles`; block title — `Tilles`. | yes | залишилось |
| 64 | 22 | Muzeum? | `czytanie[5].items[0].text` | czytanie | `warsztacie Alvara Colanena` | spelling | medium | `warsztacie Alvara Kolanena` | У B1/B7/B9/quiz — `Kolanen`. | yes | залишилось |
| 65 | 22 | Muzeum? | `czytanie[6].items[0].text` | czytanie | `mikrofilmów zaprojektowanymi` | agreement | critical | `mikrofilmów zaprojektowanych` | `mikrofilmów` (р. від.) + `zaprojektowanych`. | yes | виправлено |
| 66 | 22 | Muzeum? | `czytanie[7].items[0].text` | czytanie | `w galerii Laterna Madzika` | spelling | critical | `w galerii Laterna Magica` | Типографія назви; UA уже «Laterna Magica». | yes | виправлено |
| 67 | 23 | Czas na egzamin! | `zeszyt[0].text` п. 18 | zeszyt | `Konfliktów nie omina w życiu…` | grammar | critical | `Konfliktów nie unikniesz…` / `Konflikty nie ominą cię…` | `omina` — хибна форма; UA вже виправлено, PL — ні. | yes | виправлено |

---

## Етап 2. Внесені виправлення (2026-07-02)

### Critical Блоку B — застосовано (28 записів)

| Урок | № | Файл | Що змінено |
|---|---|---|---|
| L03 | 30–31 | `lekcja-03.json` | `Vito Corleone`; UA `Трохи занадто близько` |
| L07 | 35–37 | `lekcja-07.json` | `Joanna Łapińska` у title; `języka niemieckiego` / `angielskiego` |
| L08 | 38 | `lekcja-08.json` | UA `нахилитися по нього` |
| L09 | 39 | `lekcja-09.json` | UA `платитимемо за надлишковий багаж` (`nadbagaż`) |
| L10 | 40 | `lekcja-10.json` | UA `мене не відраїш` |
| L12 | 42–43 | `lekcja-12.json` | UA `як дріт`; `oferty domku` |
| L13 | 45 | `lekcja-13.json` | `myślałaś` |
| L15 | 46–52 | `lekcja-15.json` | `koniec I wojny`; колядка (żłóbka, trzód, w żłóbku, rączęta); `go dzielić` (drills + song) |
| L16 | 54–55 | `lekcja-16.json` | прибрано `сироти` з vocab; `jesień był piękny` |
| L18 | 56 | `lekcja-18.json` | розділено репліки: Angela «To też nie jest wesołe» + Mami з гороскопом Baran |
| L20 | 57–59, 61 | `lekcja-20.json` | коми `Dzień dobry, panu/pani` (3 місця); `przynosi mi` |
| L22 | 65–66 | `lekcja-22.json` | `zaprojektowanych`; `Laterna Magica` |
| L23 | 67 | `lekcja-23.json` | `Konfliktów nie unikniesz` |

### Залишилось (11 записів, medium/low)

Пріоритет 2 — medium:

- **L03** №29, 32; **L02** №33; **L06** №34; **L11** №41; **L16** №53; **L20** №60, 62; **L22** №63–64.

Пріоритет 3 — low:

- **L12** №44.

---

## 1. Помилки польської граматики

- L07: `język niemiecki/angielski` → родовий після `trochę` (**виправлено**).
- L12: `oferty domek` → `domku` (**виправлено**).
- L13: `myślałeś` → `myślałaś` (**виправлено**).
- L15: `oficjalny I wojny` → `oficjalny koniec I wojny`; `dzielić się` → `go dzielić` (**виправлено**).
- L16: `jesień była` → `jesień był` (**виправлено**).
- L20: `przynosi mnie` → `przynosi mi` (**виправлено**); `Co za czasy, proszę pani` — залишилось (№60).
- L22: `zaprojektowanymi` → `zaprojektowanych` (**виправлено**).
- L23: `Konfliktów nie omina` → `nie unikniesz` (**виправлено**).

## 2. Помилки пунктуації

- L20: `Dzień dobry panu/pani` (3 місця) — **виправлено**; `Co za czasy, proszę pani` — залишилось (№60).
- L12: кома перед `była` у підрядному реченні — залишилось (№44).

## 3. Помилки українського перекладу

- L03: `za blisko` → не «задалеко близько» (**виправлено**).
- L02: `Angela` → не «Анджело» — залишилось (№33).
- L06: `mówienie` → не інфінітив «говорити» — залишилось (№34).
- L08: `po niego` → «по нього» (**виправлено**).
- L09: `nadbagaż` → не «перевага» (**виправлено**).
- L10: `zniechęcić` → не «відмовиш» (**виправлено**).
- L11: `podchody` → не «підходи» — залишилось (№41).
- L12: `proste jak drut` → не «двічі по два» (**виправлено**).
- L16: `сироти` у `gęsia skórka` (**виправлено**); `situacji` у `goal` — залишилось (№53).

## 4. Помилки в піснях

- L15 №52: `zaczęła się dzielić` → `zaczęła go dzielić` (**виправлено**; узгоджено з drills і Zwrotka 2 пісні).
- L02 пісня: попередні 4 правки застосовані; розбіжностей із `czytanie`/`quiz` про 1997 рік немає.

## 5. Помилки або неточності в граматичних поясненнях

- Уроки 01–04: таблиці narzędnik / dopełniacz / kino / liczba mnoga — без критичних дефектів.
- L03 `zeszyt`: відповідь `nie są, tylko z brzegu` — педагогічно небезпечна (№32).
- L03 `title` «Teatr» при кіно-контенті (№29).

## 6. Розбіжності між текстом, квізом і піснею

- L02: після правок пісня узгоджена з текстом про повінь 1997 (**виправлено**).
- L03: заголовок `Teatr` vs кіно (№29 — залишилось); час бронювання 15 vs 30 хв у різних zeszyt (перевірити з підручником).
- L18: speaker Angela vs horoskop Mami — **виправлено** (репліки розділено; quiz про Mami/Baran узгоджений).
- L22: `Tilles` vs `Tyles`; `Colanen` vs `Kolanen` — залишилось (№63–64); `Laterna Magica` — **виправлено**.

---

## Особлива перевірка уроків 01–04

| Урок | Тема | Результат |
|---|---|---|
| 01 | Narzędnik | Форми `jestem historykiem`, `interesować się`, `z/ze`, `za`, `pod` — коректні в `gramatyka`/`drills`. Дрібна розмовна еліпса в діалозі (№ не в таблиці — low). |
| 02 | Dopełniacz | Заперечення, `szukać/słuchać/bać się`, прийменники, кількість — OK. Пісня про 1997 виправлена. Переклад Angela (№33) — залишилось. |
| 03 | Kino / że / żeby | `do kina`/`na film`, `w kinie` — OK у правилах. `Vito` і переклад `za blisko` — **виправлено**; залишилось: `nie są tylko z brzegu` (№32), заголовок `Teatr` (№29). |
| 04 | dwaj, trzej, czterej | `Polacy`, `studenci`, спорт — OK. Можлива неточність перекладу `Polanie` (не в таблиці — low). |

---

## Рекомендація

**Виконано (2026-07-02):** усі critical з Блоку B (№30–31, 35–40, 42–43, 45–52, 54–56, 57–61, 65–67), зокрема L09 (`nadbagaż`), L15 (колядка + `koniec I wojny`), L18 (speaker), L20 (коми + `mi`), L23 (PL узгоджено з UA).

**Далі за бажанням (medium/low):** №29, 32–34, 41, 44, 53, 60, 62–64 — див. Етап 2.

**Можна залишити як стилістичний варіант:** еліптичні розмовні репліки на кшталт `To dość trudne kierować firmą…` (L01, low); `Nie wiadomo skąd` без коми в художньому тексті (L17, якщо трактувати як стиль).

**Перевірити з викладачем / підручником:**

- L03: чи змінювати `title` на `Kino`; час закінчення rezerwacji (15 vs 30 хв) у різних діалогах.
- L15 «Cicha noc»: точкові правки транскрипту застосовано; чи потрібна повна заміна на канонічну колядку — на розсуд викладача.

## Перевірка після правок

- Усі 24 JSON-файли коректно парсяться.
- 28 записів Блоку A: старі помилкові фрагменти не знайдені (0 збігів).
- 28 critical Блоку B: старі помилкові фрагменти не знайдені (0 збігів); 11 medium/low — досі в файлах.
- Змінені файли: `lekcja-03`, `07`, `08`, `09`, `10`, `12`, `13`, `15`, `16`, `18`, `20`, `22`, `23`.
