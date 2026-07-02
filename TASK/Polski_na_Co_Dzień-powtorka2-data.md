# Polski_na_Co_Dzień / powtorka2/data — протокол перевірки JSON

Дата перевірки: 2026-07-02.

Обсяг: перевірено 24 JSON-файли в `powtorka2/data`: `lekcja-01.json`–`lekcja-23.json` і `lessons.json`.

## Короткий підсумок

- Critical: 20.
- Medium: 7.
- Low: 1.
- Найчастіші типи: punctuation, spelling, factual-inconsistency, syntax/agreement.
- Особлива перевірка уроків 01–04: таблиці, квізи й drills загалом коректні; критичні збої знайдено в `song.lyrics` уроку 02, де пісня суперечила основному тексту про повінь 1997 року.

## Таблиця протоколу

| ID | Урок | JSON-шлях | Тип блоку | Оригінал | Тип помилки | Серйозність | Виправлення | Пояснення | JSON |
|---|---|---|---|---|---|---|---|---|---|
| 02 | Dopełniacz jest wszędzie | `song.lyrics` | song | `Powódź tysiąclecia była w lipcu, w siedemdziesiątym siódmym` | factual-inconsistency | critical | `Powódź tysiąclecia była w lipcu, w dziewięćdziesiątym siódmym` | Основний текст і quiz дають 1997 рік; `siedemdziesiątym siódmym` означає 1977. | yes |
| 02 | Dopełniacz jest wszędzie | `song.lyrics` | song | `Woda zniszczyła domów, szkół i dróg, mostów, torów kolejowych — ogromną ilość strat.` | case-government | critical | `Woda zniszczyła domy, szkoły i drogi, mosty, tory kolejowe — ogromne straty.` | `zniszczyć` керує biernikiem: `domy`, `szkoły`, `drogi`; фраза `ogromną ilość strat` неприродна. | yes |
| 02 | Dopełniacz jest wszędzie | `song.lyrics` | song | `W falach powodzi zginęło pięć i pięćdziesiąt osób` | factual-inconsistency | critical | `W falach powodzi zginęło pięćdziesiąt sześć osób` | Основний текст каже, що в Польщі загинуло 56 осіб; `pięć i pięćdziesiąt` є помилковою формою числа. | yes |
| 02 | Dopełniacz jest wszędzie | `song.lyrics` | song | `Siedem tysięcy ludzi straciło dach nad głową` | factual-inconsistency | medium | `Ponad siedem tysięcy osób straciło dach nad głową` | У тексті: `ponad 7 tysięcy osób`; пісня втрачала `ponad` і міняла формулювання. | yes |
| 07 | Praca | `gramatyka[2].words` | gramatyka | `Cześć Stary!` | punctuation | medium | `Cześć, stary!` | У звертанні потрібна кома; `stary` як звертання до приятеля не є власною назвою. | yes |
| 07 | Praca | `song.lyrics` | song | `Cześć, Stary!` | spelling | medium | `Cześć, stary!` | Після коми слово-звертання `stary` пишеться з малої літери. | yes |
| 16 | Przygody | `czytanie[0].items[1].text` | czytanie | `gdzie o wypadek nie trudno` | spelling | critical | `gdzie o wypadek nietrudno` | Прислівник/предикатив `nietrudno` у значенні "легко" пишеться разом. | yes |
| 16 | Przygody | `czytanie[0].items[1].text` | czytanie | `Nie wiadomo skąd nadeszły czarne chmury` | punctuation | medium | `Nie wiadomo, skąd nadeszły czarne chmury` | Непряме питання з `skąd` відокремлюється комою. | yes |
| 16 | Przygody | `czytanie[0].items[1].tr` | translation | `Невідомо звідки насунулися чорні хмари` | punctuation | medium | `Невідомо, звідки насунулися чорні хмари` | В українському перекладі також потрібна кома в підрядній частині. | yes |
| 16 | Przygody | `czytanie[0].items[1].text` | czytanie | `zupełnie nie wiedziałem co robić` | punctuation | critical | `zupełnie nie wiedziałem, co robić` | Непряме питання `co robić` відокремлюється комою. | yes |
| 16 | Przygody | `song.lyrics` | song | `wszystko dobre!` | word-choice | critical | `wszystko dobrze!` | Йдеться про результат події, потрібен прислівник `dobrze`, не прикметник `dobre`. | yes |
| 16 | Przygody | `song.lyrics` | song | `zacisnij zęby` | spelling | critical | `zaciśnij zęby` | У наказовій формі потрібна польська літера `ś`. | yes |
| 19 | Zielono mi! | `czytanie[1].items[0].text` | czytanie | `zostawałam dopóźna w firmie` | spelling | critical | `zostawałam do późna w firmie` | Правильний запис прислівникового виразу: `do późna`. | yes |
| 19 | Zielono mi! | `czytanie[1].items[0].tr` | translation | `залишалася допізна в фірмі` | style/naturalness | low | `залишалася допізна у фірмі` | Українською природніше й милозвучніше `у фірмі`. | yes |
| 19 | Zielono mi! | `czytanie[1].items[0].text` | czytanie | `Ja nigdy nie mieszkałem na wsi` | agreement | critical | `Ja nigdy nie mieszkałam na wsi` | Текст починається `Mówi Łucja`; жіночий мовний суб'єкт потребує форми `mieszkałam`. | yes |
| 19 | Zielono mi! | `czytanie[1].items[0].text` | czytanie | `Na początku nie mogłem się przyzwyczaić` | agreement | critical | `Na początku nie mogłam się przyzwyczaić` | Та сама узгодженість із жіночим мовцем Łucja. | yes |
| 19 | Zielono mi! | `czytanie[1].items[0].tr` | translation | `Я ніколи не жив на селі` | translation-mismatch | critical | `Я ніколи не жила на селі` | Український переклад має відповідати жіночому мовцю. | yes |
| 19 | Zielono mi! | `czytanie[1].items[0].tr` | translation | `Спочатку не міг звикнути` | translation-mismatch | critical | `Спочатку не могла звикнути` | Узгодження в перекладі також має бути жіночим. | yes |
| 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `gdyby niewielki wybór towarów i niskie ceny` | syntax | critical | `gdyby nie duży wybór towarów i niskie ceny` | Конструкція умови має бути `gdyby nie...`; за змістом супермаркет приваблює саме великим вибором і низькими цінами. | yes |
| 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `a jak ognia, boi się internetu i akwizytorów` | syntax | critical | `a internetu i akwizytorów boi się jak ognia` | Порівняння `bać się jak ognia` не розривається комою перед дієсловом. | yes |
| 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `W najważniejsze sprzęty swoje mieszkanie prawie wyposażył.` | syntax | medium | `Swoje mieszkanie prawie wyposażył w najważniejsze sprzęty.` | Природний порядок для `wyposażyć mieszkanie w coś`: об'єкт + `w` + biernik. | yes |
| 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `Kupując jedzenie szuka wyrobów krajowych.` | punctuation | critical | `Kupując jedzenie, szuka wyrobów krajowych.` | Imiesłowowy równoważnik zdania відокремлюється комою. | yes |
| 20 | Rysopis Polaka konsumenta | `czytanie[0].items[0].text` | czytanie | `nie wie dokładnie co to takiego` | punctuation | critical | `nie wie dokładnie, co to takiego` | Непряме питання з `co` потребує коми. | yes |
| 20 | Rysopis Polaka konsumenta | `zeszyt[0].text` | zeszyt | `64-te urodziny` | spelling | critical | `64. urodziny` | У польській мові порядковий числівник цифрами позначають крапкою, не суфіксом `-te`. | yes |
| 20 | Rysopis Polaka konsumenta | `zeszyt[1].text` | zeszyt | `Zainteresowaniem czytają...` | case-government | critical | `Z zainteresowaniem czytają...` | Конструкція має прийменник `z`: `czytać z zainteresowaniem`. | yes |
| 20 | Rysopis Polaka konsumenta | `zeszyt[1].text` | zeszyt | `po czym omijając plakat ... idą na zakupy` | punctuation | medium | `po czym, omijając plakat ..., idą na zakupy` | Imiesłowowy równoważnik `omijając...` треба виділити комами. | yes |
| 21 | Sztuka | `czytanie[4].items[1].text` | czytanie | `że korzystając z darmowych pirackich kopii popełniają nadużycie` | punctuation | critical | `że, korzystając z darmowych pirackich kopii, popełniają nadużycie` | Дієприслівникову конструкцію треба виділити комами. | yes |
| 23 | Czas na egzamin! | `czytanie[1].items[0].text` | czytanie | `że będąc wzrokowcem powinnam przede wszystkim więcej czytać po polsku` | punctuation | critical | `że, będąc wzrokowcem, powinnam przede wszystkim więcej czytać po polsku` | Imiesłowowy równoważник `będąc wzrokowcem` виділяється комами. | yes |

## Внесені правки

Виправлено всі 28 позицій із таблиці в 7 файлах:

- `lekcja-02.json`: 4 правки в `song.lyrics`.
- `lekcja-07.json`: 2 правки в `gramatyka` і `song.lyrics`.
- `lekcja-16.json`: 6 правок у `czytanie`, `translation`, `song.lyrics`.
- `lekcja-19.json`: 6 правок у `czytanie` і `translation`.
- `lekcja-20.json`: 7 правок у `czytanie` і `zeszyt`.
- `lekcja-21.json`: 1 правка в `czytanie`.
- `lekcja-23.json`: 1 правка в `czytanie`.

## 1. Помилки польської граматики

- Урок 02: `zniszczyła domów...` → виправлено керування після `zniszczyć`.
- Урок 16: `wszystko dobre!` → `wszystko dobrze!`.
- Урок 19: `mieszkałem`, `mogłem` → жіночі форми `mieszkałam`, `mogłam` для Łucja.
- Урок 20: `gdyby niewielki...`, `a jak ognia, boi się...`, `W najważniejsze sprzęty...` → виправлено синтаксис.

## 2. Помилки пунктуації

- Урок 07: кома у звертанні `Cześć, stary!`.
- Урок 16: коми в непрямих питаннях `skąd`, `co robić`.
- Урок 20: коми після `Kupując jedzenie`, у непрямому питанні `co to takiego`, і навколо `omijając...`.
- Урок 21: коми навколо `korzystając...`.
- Урок 23: коми навколо `będąc wzrokowcem`.

## 3. Помилки українського перекладу

- Урок 16: `Невідомо звідки...` → `Невідомо, звідки...`.
- Урок 19: чоловічі форми `жив`, `міг` → жіночі `жила`, `могла`, бо говорить Łucja.
- Урок 19: `допізна в фірмі` → `допізна у фірмі`.

## 4. Помилки в піснях

- Урок 02: виправлено рік, число загиблих, відмінок після `zniszczyć`, і відповідність до основного тексту про `ponad 7 tysięcy osób`.
- Урок 07: `Cześć, Stary!` → `Cześć, stary!`.
- Урок 16: `wszystko dobre!` → `wszystko dobrze!`; `zacisnij` → `zaciśnij`.

## 5. Помилки або неточності в граматичних поясненнях

- Таблиці й правила в уроках 01–04 істотних правок не потребували.
- Єдина навчально небезпечна неточність у спеціально перевірених темах була не в таблиці, а в пісні уроку 02: вона суперечила тексту/квізу про повінь 1997 року.

## 6. Розбіжності між текстом, квізом і піснею

- Урок 02: `czytanie`, `quiz`, `drills` послідовно дають `lipiec 1997`, `56 osób`, `ponad 7 tysięcy osób`; `song.lyrics` мав інші або зіпсовані форми. Виправлено.
- Урок 20: український переклад уже містив правильну логіку `якби не великий вибір`, тоді як польський текст мав `gdyby niewielki wybór`. Польський текст виправлено.

## Рекомендація

- Обов'язково виправляти: усі critical-позиції з таблиці, особливо пісню уроку 02, узгодження Łucja в уроці 19 і синтаксис уроку 20.
- Можна залишати як стилістичний варіант: еліптичні розмовні фрази на кшталт `nie wiem jak` / `nie wiem skąd`, якщо вони звучать як коротка репліка, а не повне підрядне речення.
- Варто звірити з викладачем або оригінальним підручником: чи треба в пісні уроку 02 максимально точно зберігати всі статистичні формулювання з читання, чи допустима пісенна компресія після виправлення критичних чисел.

## Перевірка після правок

- Усі `powtorka2/data/*.json` успішно парсяться через `JSON.parse`.
- Контрольний пошук старих помилкових фрагментів не дав збігів.
- `git diff --check -- powtorka2/data` не показав whitespace-помилок.
