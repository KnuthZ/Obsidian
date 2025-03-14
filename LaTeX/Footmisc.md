#### Опции и их объяснение:

- `perpage` — Перенумерация сносок на каждой странице. Требует двух прогонов LaTeX для корректной работы.
- `para` — Форматирование сносок в виде одного абзаца внизу страницы. Если сноска одна, разницы не будет заметно.
- `side` — Размещает сноски в полях страницы с использованием `\marginpar`. Рекомендуется использовать с `ragged` для выравнивания по левому краю.
- `ragged` — Включает неровное (левое) выравнивание сносок. Можно настроить через `\renewcommand\footnotelayout`.
- `symbol` — Использует символы вместо чисел для сносок. Подходит для небольшого количества сносок.
- `symbol*` — Улучшенная версия `symbol`, предотвращает ошибки при работе с `perpage`. При нехватке символов переключается на числовую нумерацию.
- `bottom` — Принудительно размещает сноски внизу страницы (под текстом и над плавающими объектами).
- `bottomfloats` — Принудительно размещает плавающие объекты внизу страницы, не затрагивая сноски.
- `abovefloats` — Размещает сноски над плавающими объектами (поведение по умолчанию в LaTeX).
- `belowfloats` — Размещает сноски под плавающими объектами.
- `marginal` — Регулирует положение метки сноски относительно левого поля страницы. Несовместимо с `para`.
- `flushmargin` — Работает так же, как `marginal`, но выравнивает маркер виноски по краю, слегка смещая его внутрь относительно текста виноски.
- `hang` — Эта опция выравнивает маркер виноски по краю и делает текст виноски выступающим с отступом, равным значению `\footnotemargin` (если оно положительное) или ширине маркера (если `\footnotemargin ≤ 0`). По умолчанию `\footnotemargin` равно `1.8em`. Если виноска состоит из нескольких абзацев, между ними вставляется вертикальный отступ, определённый командой `\hangfootparskip`.
- `norule` — Эта опция отключает стандартную разделительную линию для вносок и корректирует `\skip\footins`, чтобы компенсировать её отсутствие.
- `splitrule` — Эта опция добавляет полную горизонтальную линию над частью разделённой виноски (если виноска разбита на несколько страниц). Не действует для вносок, оформленных в виде абзацев.

Опция определяет три варианта команды `\footnoterule`:

- `\mpfootnoterule` — для вносок в окружениях `minipage`
- `\pagefootnoterule` — для обычных вносок на страницах
- `\splitfootnoterule` — для разделённой части виноски
    

По умолчанию `\mpfootnoterule` и `\pagefootnoterule` сохраняют стандартное определение `\footnoterule` (которое может быть изменено опцией `norule`), а `\splitfootnoterule` становится полным разделителем.

- `multiple` — Эта опция корректирует отображение нескольких вносок подряд. Например, без специальной обработки следующий код:
`mumble\footnote{blah}\footnote{grumble}`

Выведет: `mumble¹³¹⁴`

С опцией `multiple` результат будет: `mumble¹³,¹⁴`, что соответствует ожидаемому формату.

Разделитель (по умолчанию запятая) задаётся командой `\multfootsep` и может быть изменён с помощью `\renewcommand`. Опция также распространяется на `\footnotemark`.

---

#### Основные команды

- `\setfnsymbol{имя_набора}` — Устанавливает конкретный набор символов для нумерации сносок.

**Наборы:**
- Bringhurst: `∗ † ‡ § ∥ ¶`
- Chicago: `∗ † ‡ § ∥ #`
- Wiley: `∗ ∗∗ † ‡ § ¶ `

---

- `\DefineFNsymbols{имя}{набор}` — Создает пользовательский набор символов для сносок.

**Пример:**
```
\DefineFNsymbols{custom}{\dagger\ddagger\star}
\setfnsymbol{custom}
```

---

- `\footnotelayout` — Настраивает стиль форматирования сносок.

**Пример:**
`\renewcommand\footnotelayout{\centering}`