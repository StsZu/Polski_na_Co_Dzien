# ТЗ: Усний тренажер «Mów po polsku» для powtorka2 (курс 2)

> Як це зроблено в курсі 1 (`powtorka/`) і що потрібно, щоб повторити в курсі 2 (`powtorka2/`).

## Як це працює в курсі 1

**Дані** — поле `drills` у `lekcja-NN.json`: масив пар `[завдання_укр, зразок_pl]`.

```json
"drills": [
  ["Спитай перехожого, де туалет.", "Przepraszam, gdzie jest toaleta?"],
  ["Скажи: «Я дуже втомлений».", "Jestem bardzo zmęczony."]
]
```

**UI:** одна картка по центру — рядок-завдання, прихований блок-зразок, дві кнопки
«Нове завдання» (випадкове, ≠ поточного) і «Показати зразок» (disabled, доки немає завдання).
Логіка: тиснеш «Нове завдання» → укр. підказка → промовляєш польською вголос →
«Показати зразок» → з'являється польський еталон.

---

## 1. Призначення

Active-recall тренажер продукування мовлення: студент бачить **комунікативне завдання
українською**, вимовляє відповідь **польською вголос**, потім перевіряє себе еталоном.
Самостійно, без оцінювання.

## 2. Дані — нове поле `drills` у `lekcja-NN.json`

- Тип: масив пар `["<завдання UA>", "<зразок PL>"]`.
- Рекомендовано **8–12 завдань** на урок.
- Опціонально (розширення, див. §8): третій елемент `"<підказка/альтернатива>"`.
- Секція не рендериться, якщо `drills` відсутнє або порожнє (зворотна сумісність).

## 3. UI / макет

- Окрема `<section>` з заголовком **«Mów po polsku»**, тег-лейбл «усний тренажер»,
  підзаголовок: *«Прочитай завдання, скажи фразу польською вголос — потім перевір зразок.»*
- Усередині — одна картка `.drill` (по центру):
  - `.task` — поточне завдання (укр.), стартовий текст «Натисни „Нове завдання", щоб почати.»
  - `.ans` — прихований блок зі зразком (PL), показується по кнопці.
  - `.ctrls` — дві кнопки: **«Нове завдання»** (primary) і **«Показати зразок»** (вторинна, спершу `disabled`).

## 4. Поведінка

- **«Нове завдання»**: вибрати випадковий індекс `r`, відмінний від поточного (якщо завдань >1);
  показати `drills[r][0]`; сховати зразок; розблокувати «Показати зразок».
- **«Показати зразок»**: показати `drills[cur][1]` у `.ans`.
- Стан: змінна `cur` (індекс поточного, старт `-1`). До першого «Нове завдання» зразок недоступний.
- ⚠️ У курсі 1 `Math.random()` — нормально для браузера. (У *генераторі контенту* `Math.random`
  заборонено, але це рантайм-код сторінки — без обмежень.)

## 5. Стилі

Перевикористати CSS-змінні теми (`--soft`, `--acc2`, `--line`, `--ink`). Картка `.drill`:
фон `--soft`, рамка `--line`, центрування; `.task` — 17px, мін-висота 50px; `.ans` —
синій блок (`--acc2`), `display:none` → `.show`; кнопки `.primary` = `--acc2`.
**Працює і в темній темі автоматично** (змінні вже мають dark-варіанти в powtorka2).

```css
.drill{background:var(--soft);border:1px solid var(--line);border-radius:12px;padding:18px 16px;text-align:center}
.drill .task{font-size:17px;font-weight:600;min-height:50px;display:flex;align-items:center;justify-content:center;padding:0 8px}
.drill .ans{display:none;background:#eef4fb;border:1px solid #d8e6f4;border-radius:9px;padding:11px;font-size:17px;color:var(--acc2);font-weight:700;margin:12px 0}
.drill .ans.show{display:block}
.drill .ctrls{display:flex;gap:10px;justify-content:center;flex-wrap:wrap}
.drill button{font-family:Roboto,sans-serif;border-radius:9px;padding:10px 18px;font-size:14px;cursor:pointer;border:1px solid var(--line);background:#fff;color:var(--ink)}
.drill button.primary{background:var(--acc2);color:#fff;border-color:var(--acc2)}
.drill button:disabled{opacity:.4;cursor:not-allowed}
```

## 6. Інтеграція в `powtorka2/lekcja.html`

- Додати блок рендера у функцію `render(d)` — **між quiz і checklist** (або одразу перед `checklist`).
  Порядок секцій: Słownictwo → Gramatyka → Czytanie → Zeszyt → Quiz → **Mów po polsku** → Checklist.
- Код майже verbatim із курсу 1 (хелпери `$`, `esc`, `section`, `sub` у powtorka2 ідентичні):

```js
/* MÓW PO POLSKU */
if(d.drills&&d.drills.length){
  const s=section('усний тренажер','Mów po polsku');
  sub(s,'Прочитай завдання, скажи фразу польською вголос — потім перевір зразок.');
  const dr=$('div','drill');
  const task=$('div','task','Натисни «Нове завдання», щоб почати.');
  const ans=$('div','ans'); const ctr=$('div','ctrls');
  const bNew=$('button','primary','Нове завдання');
  const bRev=$('button',null,'Показати зразок'); bRev.disabled=true;
  let cur=-1;
  bNew.onclick=()=>{let r=cur;while(r===cur&&d.drills.length>1)r=Math.floor(Math.random()*d.drills.length);if(d.drills.length===1)r=0;cur=r;task.textContent=d.drills[r][0];ans.classList.remove('show');ans.textContent='';bRev.disabled=false;};
  bRev.onclick=()=>{if(cur<0)return;ans.textContent=d.drills[cur][1];ans.classList.add('show');};
  ctr.appendChild(bNew); ctr.appendChild(bRev);
  dr.appendChild(task); dr.appendChild(ans); dr.appendChild(ctr);
  s.appendChild(dr); wrap.appendChild(s);
}
```

- Додати CSS-блок `.drill …` (із §5) у `<style>`.

## 7. Правила наповнення контентом (на урок)

Завдання генерувати **з матеріалу саме цього уроку** (граматика + лексика + ситуації з діалогів).
Формат завдання — комунікативна інструкція укр.: «Спитай…», «Скажи…», «Поясни…», «Попроси…».
Зразок — коротка природна польська фраза. Покрити **ключову граматику уроку**
(напр. для L01 — narzędnik: «Скажи, що ти за фахом музикант» → «Jestem muzykiem»).
8–12 шт., без дублів, від простого до складнішого.

## 8. Опціональні покращення для курсу 2 (не обов'язково)

- **Третій елемент** пари — підказка/альтернатива (як у Gemini-етюді:
  «Альтернатива: Co cię interesuje?»). Рендерити дрібним сірим під зразком.
- **Лічильник** «Картка N / усього» та кнопка «наступне по черзі» (а не лише random).
- **Аудіо-еталон**: озвучити зразки ElevenLabs і додати міні-плеєр під «Показати зразок»
  (узгоджено з рештою аудіо курсу 2).
