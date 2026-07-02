# Polski_na_Co_Dzień / powtorka/data — протокол перевірки JSON

Дата перевірки: 2026-07-02.

Обсяг: `powtorka/data/*.json`. Блоки `mistakes` не перевірялися як помилки до виправлення, згідно із завданням.

## Етап 1. Протокол знайдених помилок

1. Lesson ID: `03`
   - Lesson title: `Mami, kto to jest?`
   - JSON file: `powtorka/data/lekcja-03.json`
   - JSON path: `czytanie[0].items[1].lines[0][1]`
   - Original: `Cześć Mami. Co słychać?`
   - Type: пунктуація
   - Severity: critical
   - Proposed fix: `Cześć, Mami. Co słychać?`
   - Explanation: у польській мові звертання виділяється комою.

2. Lesson ID: `04`
   - Lesson title: `Jaki jesteś?`
   - JSON file: `powtorka/data/lekcja-04.json`
   - JSON path: `czytanie[0].items[0].lines[0][1]`
   - Original: `Cześć Javier.`
   - Type: пунктуація
   - Severity: critical
   - Proposed fix: `Cześć, Javier.`
   - Explanation: ім'я у звертанні треба відокремити комою.

3. Lesson ID: `04`
   - Lesson title: `Jaki jesteś?`
   - JSON file: `powtorka/data/lekcja-04.json`
   - JSON path: `czytanie[0].items[0].lines[1][1]`
   - Original: `Cześć Mami. Co słychać?`
   - Type: пунктуація
   - Severity: critical
   - Proposed fix: `Cześć, Mami. Co słychać?`
   - Explanation: звертання `Mami` має бути виділене комою.

4. Lesson ID: `04`
   - Lesson title: `Jaki jesteś?`
   - JSON file: `powtorka/data/lekcja-04.json`
   - JSON path: `czytanie[0].items[1].lines[4][1]`
   - Original: `No dobrze Mami, masz rację. „Hola” to słowo po hiszpańsku. Znaczy „cześć”.`
   - Type: пунктуація
   - Severity: critical
   - Proposed fix: `No dobrze, Mami, masz rację. „Hola” to słowo po hiszpańsku. Znaczy „cześć”.`
   - Explanation: звертання всередині речення виділяється з обох боків.

5. Lesson ID: `05`
   - Lesson title: `Jesteś instruktorem tanga?`
   - JSON file: `powtorka/data/lekcja-05.json`
   - JSON path: `czytanie[3].items[3].lines[0][1]`
   - Original: `Cześć Mami! Co czytasz?`
   - Type: пунктуація
   - Severity: critical
   - Proposed fix: `Cześć, Mami! Co czytasz?`
   - Explanation: звертання після привітання відділяється комою.

6. Lesson ID: `05`
   - Lesson title: `Jesteś instruktorem tanga?`
   - JSON file: `powtorka/data/lekcja-05.json`
   - JSON path: `czytanie[3].items[3].lines[1][1]`
   - Original: `Cześć Javier! Czytam książkę biograficzną.`
   - Type: пунктуація
   - Severity: critical
   - Proposed fix: `Cześć, Javier! Czytam książkę biograficzną.`
   - Explanation: ім'я у звертанні треба відокремити комою.

7. Lesson ID: `05`
   - Lesson title: `Jesteś instruktorem tanga?`
   - JSON file: `powtorka/data/lekcja-05.json`
   - JSON path: `czytanie[3].items[3].lines[7][1]`
   - Original: `Och, Javier, nie martw się! Ja znam Witkacego, bo interesuję się sztuką i malarstwem. Ale na przykład tango, czy akordeon, to dla mnie czarna magia!`
   - Type: пунктуація
   - Severity: medium
   - Proposed fix: `Och, Javier, nie martw się! Ja znam Witkacego, bo interesuję się sztuką i malarstwem. Ale na przykład tango czy akordeon to dla mnie czarna magia!`
   - Explanation: у простому зіставленні `tango czy akordeon` кома перед одиничним `czy` не потрібна; кома перед `to` тут також зайва.

8. Lesson ID: `08`
   - Lesson title: `Mami, jesteś głodna?`
   - JSON file: `powtorka/data/lekcja-08.json`
   - JSON path: `czytanie[0].items[3].lines[8][1]`
   - Original: `Brawo Mami. Wolę owocowy.`
   - Type: пунктуація
   - Severity: critical
   - Proposed fix: `Brawo, Mami. Wolę owocowy.`
   - Explanation: звертання `Mami` треба виділити комою.

9. Lesson ID: `09`
   - Lesson title: `Lubisz marchewkę?`
   - JSON file: `powtorka/data/lekcja-09.json`
   - JSON path: `czytanie[3].items[1].lines[0][1]`
   - Original: `Cześć dziewczyny, co robicie? Coś dobrego?`
   - Type: пунктуація
   - Severity: critical
   - Proposed fix: `Cześć, dziewczyny, co robicie? Coś dobrego?`
   - Explanation: `dziewczyny` є звертанням і має бути виділене комою.

10. Lesson ID: `10`
    - Lesson title: `Uwielbiam polskie jedzenie!`
    - JSON file: `powtorka/data/lekcja-10.json`
    - JSON path: `czytanie[2].items[0].lines[4][1]`
    - Original: `Angela, ja nie chcę pić ani piwa, ani wódki, ani wina, żadnego drinka! Nie chcę też kawy, herbaty, kompotu czy mleka! Chciałabym tylko zjeść coś słodkiego, jakiś dobry deser, albo chociaż rurkę z kremem, gofra czy coś.`
    - Type: пунктуація
    - Severity: medium
    - Proposed fix: `Angela, ja nie chcę pić ani piwa, ani wódki, ani wina, żadnego drinka! Nie chcę też kawy, herbaty, kompotu czy mleka! Chciałabym tylko zjeść coś słodkiego, jakiś dobry deser albo chociaż rurkę z kremem, gofra czy coś.`
    - Explanation: перед одиничним сполучником `albo` у простому переліку кома не потрібна.

11. Lesson ID: `10`
    - Lesson title: `Uwielbiam polskie jedzenie!`
    - JSON file: `powtorka/data/lekcja-10.json`
    - JSON path: `czytanie[2].items[0].lines[5][1]`
    - Original: `Oj Mami, nie złość się! Już wiem! Na rynku jest kawiarnia, nazywa się chyba „Pijalnia czekolady”.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Oj, Mami, nie złość się! Już wiem! Na rynku jest kawiarnia, nazywa się chyba „Pijalnia czekolady”.`
    - Explanation: вигук `Oj` і звертання `Mami` треба відокремити комами.

12. Lesson ID: `13`
    - Lesson title: `Gdzie byłaś Mami? Byłam w kinie`
    - JSON file: `powtorka/data/lekcja-13.json`
    - JSON path: `title`
    - Original: `Gdzie byłaś Mami? Byłam w kinie`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Gdzie byłaś, Mami? Byłam w kinie`
    - Explanation: звертання в заголовку також виділяється комою.

13. Lesson ID: `13`
    - Lesson title: `Gdzie byłaś Mami? Byłam w kinie`
    - JSON file: `powtorka/data/lessons.json`
    - JSON path: `[12].title`
    - Original: `Gdzie byłaś Mami? Byłam w kinie`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Gdzie byłaś, Mami? Byłam w kinie`
    - Explanation: дубль заголовка в індексі уроків має збігатися з виправленим заголовком уроку.

14. Lesson ID: `13`
    - Lesson title: `Gdzie byłaś Mami? Byłam w kinie`
    - JSON file: `powtorka/data/lekcja-13.json`
    - JSON path: `czytanie[0].items[0].lines[4][1]`
    - Original: `Cześć Mami! Gdzie byłaś?`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Mami! Gdzie byłaś?`
    - Explanation: звертання після привітання відділяється комою.

15. Lesson ID: `13`
    - Lesson title: `Gdzie byłaś Mami? Byłam w kinie`
    - JSON file: `powtorka/data/lekcja-13.json`
    - JSON path: `czytanie[0].items[0].lines[5][1]`
    - Original: `Cześć Shige! Byłam w Centrum Sztuki i Kultury Japońskiej „Manggha”.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Shige! Byłam w Centrum Sztuki i Kultury Japońskiej „Manggha”.`
    - Explanation: ім'я у звертанні треба відокремити комою.

16. Lesson ID: `13`
    - Lesson title: `Gdzie byłaś Mami? Byłam w kinie`
    - JSON file: `powtorka/data/lekcja-13.json`
    - JSON path: `czytanie[1].items[0].lines[1][1]`
    - Original: `Cześć dziewczyny! Co słychać? Jak weekend?`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, dziewczyny! Co słychać? Jak weekend?`
    - Explanation: групове звертання `dziewczyny` треба відокремити комою.

17. Lesson ID: `13`
    - Lesson title: `Gdzie byłaś Mami? Byłam w kinie`
    - JSON file: `powtorka/data/lekcja-13.json`
    - JSON path: `czytanie[1].items[0].lines[2][1]`
    - Original: `Cześć Uwe! Weekend był świetny! W piątek w nocy byłam w Galerii Krakowskiej.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Uwe! Weekend był świetny! W piątek w nocy byłam w Galerii Krakowskiej.`
    - Explanation: ім'я у звертанні треба відокремити комою.

18. Lesson ID: `13`
    - Lesson title: `Gdzie byłaś Mami? Byłam w kinie`
    - JSON file: `powtorka/data/lekcja-13.json`
    - JSON path: `czytanie[1].items[0].lines[8][1]`
    - Original: `A ty Mami? Co robiłaś w weekend?`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `A ty, Mami? Co robiłaś w weekend?`
    - Explanation: звертання всередині короткого питання відділяється комою.

19. Lesson ID: `15`
    - Lesson title: `Karton czy pudełko?`
    - JSON file: `powtorka/data/lekcja-15.json`
    - JSON path: `czytanie[0].items[2].lines[1][1]`
    - Original: `Tak mamo?`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Tak, mamo?`
    - Explanation: звертання `mamo` треба відокремити комою.

20. Lesson ID: `15`
    - Lesson title: `Karton czy pudełko?`
    - JSON file: `powtorka/data/lekcja-15.json`
    - JSON path: `czytanie[1].items[0].lines[0][1]`
    - Original: `Cześć Sylwia! Jedziesz z nami na piknik? Taka piękna pogoda, wreszcie mamy złotą polską jesień!`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Sylwia! Jedziesz z nami na piknik? Taka piękna pogoda, wreszcie mamy złotą polską jesień!`
    - Explanation: ім'я у звертанні треба відокремити комою.

21. Lesson ID: `15`
    - Lesson title: `Karton czy pudełko?`
    - JSON file: `powtorka/data/lekcja-15.json`
    - JSON path: `czytanie[4].items[1].lines[0][1]`
    - Original: `Cześć Javier, dzwoniłeś do mnie.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Javier, dzwoniłeś do mnie.`
    - Explanation: звертання `Javier` стоїть усередині речення і має бути виділене з обох боків.

22. Lesson ID: `19`
    - Lesson title: `Wszędzie dobrze, ale w domu najlepiej`
    - JSON file: `powtorka/data/lekcja-19.json`
    - JSON path: `czytanie[1].items[0].lines[2][1]`
    - Original: `Pamiętaj żeby było centralne ogrzewanie, bo jeśli będzie elektryczne to zimą dużo zapłacisz. Wiem coś o tym od pani Maj.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Pamiętaj, żeby było centralne ogrzewanie, bo jeśli będzie elektryczne, to zimą dużo zapłacisz. Wiem coś o tym od pani Maj.`
    - Explanation: потрібна кома перед підрядним `żeby`; у конструкції `jeśli ..., to ...` підрядну частину також треба закрити комою.

23. Lesson ID: `22`
    - Lesson title: `Dokąd pojedziemy na weekend?`
    - JSON file: `powtorka/data/lekcja-22.json`
    - JSON path: `czytanie[1].items[4].lines[3][1]`
    - Original: `Ciekawe tylko kiedy. Wyślemy im SMS-a, kiedy coś zaplanujemy. Koniec, kropka.`
    - Type: пунктуація
    - Severity: medium
    - Proposed fix: `Ciekawe tylko, kiedy. Wyślemy im SMS-a, kiedy coś zaplanujemy. Koniec, kropka.`
    - Explanation: `kiedy` вводить скорочену підрядну частину; кома робить синтаксис коректним.

24. Lesson ID: `22`
    - Lesson title: `Dokąd pojedziemy na weekend?`
    - JSON file: `powtorka/data/lekcja-22.json`
    - JSON path: `czytanie[3].items[0].lines[0][1]`
    - Original: `Cześć Javier.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Javier.`
    - Explanation: ім'я у звертанні треба відокремити комою.

25. Lesson ID: `22`
    - Lesson title: `Dokąd pojedziemy na weekend?`
    - JSON file: `powtorka/data/lekcja-22.json`
    - JSON path: `czytanie[3].items[0].lines[1][1]`
    - Original: `O, cześć dziewczyny. Zaraz przedstawię wam moją znajomą. To jest Majka. Studentka turystyki. A to moje koleżanki ze szkoły. Mami i Angela.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `O, cześć, dziewczyny. Zaraz przedstawię wam moją znajomą. To jest Majka. Studentka turystyki. A to moje koleżanki ze szkoły. Mami i Angela.`
    - Explanation: `dziewczyny` є звертанням після привітання і має бути відокремлене комою.

26. Lesson ID: `23`
    - Lesson title: `Za małe, za duże, w sam raz`
    - JSON file: `powtorka/data/lekcja-23.json`
    - JSON path: `czytanie[1].items[3].lines[5][1]`
    - Original: `Przepraszam, czy mogę prosić o rozmiar większe? Te są za małe.`
    - Type: граматика
    - Severity: critical
    - Proposed fix: `Przepraszam, czy mogę prosić o rozmiar większy? Te są za małe.`
    - Explanation: `rozmiar` — чоловічого роду; прикметник має узгоджуватися: `większy`, не `większe`.

27. Lesson ID: `23`
    - Lesson title: `Za małe, za duże, w sam raz`
    - JSON file: `powtorka/data/lekcja-23.json`
    - JSON path: `drills[2][1]`
    - Original: `Czy mogę prosić o rozmiar większe?`
    - Type: граматика
    - Severity: critical
    - Proposed fix: `Czy mogę prosić o rozmiar większy?`
    - Explanation: той самий випадок узгодження з `rozmiar`.

28. Lesson ID: `25`
    - Lesson title: `Ani ręką, ani nogą`
    - JSON file: `powtorka/data/lekcja-25.json`
    - JSON path: `czytanie[1].items[2].lines[1][1]`
    - Original: `Cześć Angela. Co z tobą?`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Angela. Co z tobą?`
    - Explanation: ім'я у звертанні треба відокремити комою.

29. Lesson ID: `25`
    - Lesson title: `Ani ręką, ani nogą`
    - JSON file: `powtorka/data/lekcja-25.json`
    - JSON path: `czytanie[2].items[0].lines[5][1]`
    - Original: `Niedobrze mi kiedy myślę o jedzeniu.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Niedobrze mi, kiedy myślę o jedzeniu.`
    - Explanation: перед підрядною частиною з `kiedy` потрібна кома.

30. Lesson ID: `25`
    - Lesson title: `Ani ręką, ani nogą`
    - JSON file: `powtorka/data/lekcja-25.json`
    - JSON path: `czytanie[3].items[1].lines[0][1]`
    - Original: `Dzień dobry pani doktor.`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Dzień dobry, pani doktor.`
    - Explanation: звертання `pani doktor` треба відокремити комою.

31. Lesson ID: `25`
    - Lesson title: `Ani ręką, ani nogą`
    - JSON file: `powtorka/data/lekcja-25.json`
    - JSON path: `czytanie[4].items[0].lines[5][1]`
    - Original: `Nie, Angela jest obcokrajowką. Nie mówi po polsku.`
    - Type: граматика / лексика
    - Severity: medium
    - Proposed fix: `Nie, Angela jest cudzoziemką. Nie mówi po polsku.`
    - Explanation: `obcokrajowką` виглядає як нестандартна форма; для значення "іноземка" природно й граматично вжити `cudzoziemką`.

32. Lesson ID: `26`
    - Lesson title: `Same problemy`
    - JSON file: `powtorka/data/lekcja-26.json`
    - JSON path: `czytanie[0].items[2].lines[0][1]`
    - Original: `Cześć Mami. Co tam masz?`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Mami. Co tam masz?`
    - Explanation: звертання `Mami` треба відокремити комою.

33. Lesson ID: `26`
    - Lesson title: `Same problemy`
    - JSON file: `powtorka/data/lekcja-26.json`
    - JSON path: `czytanie[2].items[0].lines[1][1]`
    - Original: `Cześć Aniu. Nie dojadę na czas do szkoły. Czy mogłabyś poprowadzić za mnie lekcję?`
    - Type: пунктуація
    - Severity: critical
    - Proposed fix: `Cześć, Aniu. Nie dojadę na czas do szkoły. Czy mogłabyś poprowadzić za mnie lekcję?`
    - Explanation: ім'я у звертанні треба відокремити комою.

## Етап 2. Внесені правки

Виправлено всі 33 фрагменти з протоколу:

- `lekcja-03.json`: 1 правка.
- `lekcja-04.json`: 3 правки.
- `lekcja-05.json`: 3 правки.
- `lekcja-08.json`: 1 правка.
- `lekcja-09.json`: 1 правка.
- `lekcja-10.json`: 2 правки.
- `lekcja-13.json`: 6 правок.
- `lessons.json`: 1 правка.
- `lekcja-15.json`: 3 правки.
- `lekcja-19.json`: 1 правка.
- `lekcja-22.json`: 3 правки.
- `lekcja-23.json`: 2 правки.
- `lekcja-25.json`: 4 правки.
- `lekcja-26.json`: 2 правки.

## Не змінено

- `lekcja-08.json`: форма `Malinaowy` у діалозі не виправлялася, бо в наступній репліці її прямо виправляють на `Malinowy`; це навчальний приклад помилки, а не дефект JSON-контенту.

## Перевірка після правок

- Усі `powtorka/data/*.json` успішно парсяться через `JSON.parse`.
- Пошук старих помилкових фрагментів не дав збігів.
