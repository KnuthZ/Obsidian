#### Основные концепции `titletoc`

При использовании `titletoc` заголовки в оглавлении (ToC) рассматриваются как прямоугольные области, внутри которых располагается текст и, возможно, заполнитель (например, точки). Эти области определяются через левую границу (`left`) и правую (`right`), а также могут модифицироваться с помощью `\hspace*{}`.

---

#### Основные команды

- `\contentslabel{<length>}`

**Объяснение:**

- Создает зарезервированное пространство в начале строки (сдвигает содержимое вправо на `<length>`).
- Вставляет номер секции.
- Эквивалентно `\hspace*{-<length>}` + вставка номера.

---

- `\contentspage`

**Объяснение:**

- Создает зарезервированное пространство в конце строки (отступ вправо на `<right>`).
- Вставляет номер страницы, выравнивая его вправо.

---

- `\dottedcontents{<section>}[<left>]{<above-code>}{<label width>}{<leader width>}`

**Где:**

- `<section>` — Название уровня заголовка (без `\`), например: `part`, `chapter`, `section`, `subsection`, `figure`, `table`.
- `<left>` (обязательный, даже в `[]`) — Отступ слева от левого края страницы.
- `<above-code>` — Код для оформления записи (включает стили и отступы). Можно использовать вертикальный материал.
- `<label width>` — Ширина выделенного места под номер заголовка.
- `<leader width>` — Ширина заполняющего символа (например, точек между заголовком и страницей).

**Пример** (по умолчанию для `book`):
```
\contentsmargin{2.55em}
\dottedcontents{section}[3.8em]{}{2.3em}{1pc}
\dottedcontents{subsection}[6.1em]{}{3.2em}{1pc}
```

Здесь:

- `\contentsmargin{2.55em}` — Отступ после номера перед названием секции.
- `\dottedcontents{section}[3.8em]{}{2.3em}{1pc}`:
    - `3.8em` — Отступ от левого края страницы.
    - `{}` — Без дополнительных команд оформления.
    - `2.3em` — Место под номер.
    - `1pc` — Ширина точек.

---

```
\titlecontents{<section>}[<left>]{<above-code>}
{<numbered-entry-format>}{<numberless-entry-format>}
{<filler-page-format>}[<below-code>]
```

**Аргументы:**

- `<section>` — Название секции без обратного слэша (`part`, `chapter`, `section`, `figure`, `table`).
- `<left>` — Отступ слева от границы страницы до начала записи.
- `<above-code>` — Код для глобального форматирования записи (может включать вертикальные отступы).
- `<numbered-entry-format>` — Оформление заголовков с номером (например, добавление форматирования или отступов).
- `<numberless-entry-format>` — Оформление заголовков без номера.
- `<filler-page-format>` — Оформление заполнителя (лидера) между заголовком и номером страницы.
- `<below-code>` — Код, добавляемый после записи (например, для вертикального отступа).

**Пример:**
```
\titlecontents{section}
[3.8em] % Отступ слева
{} % Глобальное форматирование
{\contentslabel{2.3em}} % Форматирование заголовков с номером
{\hspace*{-2.3em}} % Форматирование заголовков без номера
{\titlerule*[1pc]{.}\contentspage} % Лидер (точки) + номер страницы
```

Это создаёт оглавление, где:

- Номера разделов печатаются в поле `2.3em` шириной.
- Заполнитель в виде точек (`\titlerule*[1pc]{.}`).
- Номер страницы выровнен по правому краю.

---

```
\contentsmargin{<right>}
\contentsmargin[<correction>]{<right>}
```

**Аргументы:**

- `<right>` — Отступ справа от границы текста до номера страницы.
- `<correction>`  — Корректировка длины лидера, чтобы точки заканчивались точно перед номером страницы.

**Пример:**
`\contentsmargin[6pt]{2.5em}`

Это создаёт `2.5em` правого отступа с коррекцией в 6pt для точного выравнивания точек перед номером страницы.

---

**Команды для вставки номеров и страниц:**

- `\thecontentslabel` — Содержит номер секции без дополнительного форматирования.
- `\thecontentspage` — Содержит номер страницы без форматирования.

---

**Команды для меток и номеров страниц**

- `\contentslabel[<format>]{<space>}`

**Аргументы:**

- `<space>` — Резервирует место для номера секции.
- `<format>`  — Форматирует номер секции.

**Пример:**
`\contentslabel{2.3em}`

Резервирует `2.3em` пространства для номера секции.

---

- `\contentspage[<format>]`

**Аргументы:**

- `<format>` — Форматирует номер страницы.

**Пример:**
`\contentspage[\bfseries]`

---

- `\contentspush{<text>}`

**Аргументы:**

- `<text>` — текст, который вставляется в начало записи, сдвигая весь заголовок вправо.

**Пример:**
`\contentspush{\hspace{2em}}`

Сдвигает заголовки вправо на `2em`.

---

**Опции для титульного оформления оглавления:**

- `\titlerule*[<width>]{<char>}` — Заполнитель-лидер (`.` или `-`).
- `\addvspace{<length>}` — Добавляет вертикальный отступ.
- `\\*` — Разрыв строки без разрыва страницы.

---

##### Команда `\titlecontents*`

**Назначение:**

Используется для настройки оформления оглавления, но в отличие от `\titlecontents`, она группирует элементы в один абзац.  

**Синтаксис:**

```
\titlecontents*{<section>}[<left>]{<above-code>}
{<numbered-entry-format>}{<numberless-entry-format>}
{<filler-page-format>}[<separator>]
```

или

```
\titlecontents*{<section>}[<left>]{<above-code>}
{<numbered-entry-format>}{<numberless-entry-format>}
{<filler-page-format>}[<separator>][<end>]
```

**Аргументы:**

- `<section>` — Уровень заголовка (`section`, `subsection`, `chapter` и т. д.).
- `<left>` — Отступ перед заголовком.
- `<above-code>` — Код перед заголовком (например, изменение шрифта).
- `<numbered-entry-format>` — Оформление заголовков с номером.
- `<numberless-entry-format>` — Оформление заголовков без номера.
- `<filler-page-format>` — Оформление соединительных линий (лидеров) перед номером страницы.
- `<separator>` — Разделитель между элементами в абзаце.
- `<end>` — Текст в конце списка.

**Пример** — добавляет номера страниц через запятую и завершает список точкой:

```
\titlecontents*{subsection}[1.5em]
{\small}
{\thecontentslabel. }
{}
{, \thecontentspage}
[.---][.]
```

---

##### Команды для частичных оглавлений

- `\startcontents[<name>]`

**Описание**:  
Эта команда начинает формирование частичного оглавления (Partial TOC) в указанном месте документа. В отличие от полного оглавления (`\tableofcontents`), частичные могут использоваться в любом месте документа.  
Аргумент `<name>` позволяет создавать несколько различных наборов оглавлений, например, отдельные TOC для частей (`parts`), глав (`chapters`) и т. д.  
Если `<name>` не указан, используется `default`.

**Пример**:
`\startcontents[chapters]  % Начинаем частичное оглавление для главы`

При этом список записей начнет собираться с этого момента.

---

- `\stopcontents[<name>]`

**Описание**:  
Останавливает сбор частичного оглавления для указанного `<name>`.  
После этого содержимое не будет добавляться в данный TOC.

**Пример**:
`\stopcontents[chapters]  % Завершаем сбор записей для главы`

Теперь можно вывести содержимое через `\printcontents`.

---

- `\resumecontents[<name>]`

**Описание**:  
Продолжает сбор записей в ранее остановленное частичное оглавление.  
Если `\stopcontents` прерывал сбор, то `\resumecontents` позволяет продолжить.

**Пример**:
`\resumecontents[chapters]  % Продолжаем сбор записей для главы`

---

- `\printcontents[<name>]{<prefix>}{<start-level>}[<toc-depth>]{<toc-code>}`

**Описание**:  
Выводит текущее частичное оглавление с указанными настройками.

- `<name>` — Имя набора частичного оглавления.
- `<prefix>` — Префикс, который определяет стиль заголовков в оглавлении.
- `<start-level>` — С какого уровня заголовков начинать вывод (0 — главы, 1 — секции и т. д.).
- `<toc-depth>` — На какую глубину включать заголовки.
- `<toc-code>` — Дополнительный локальный код, например, изменение `\contentsmargin`.

**Пример**:
`\printcontents[chapters]{l}{1}[2]{}`

Выведет частичное оглавление с именем `chapters`, начиная с секций (`1`), включая подразделы (`toc-depth = 2`), без дополнительных настроек.

---

##### Команды для частичных списков

Команды `\startlist`, `\stoplist`, `\resumelist`, и `\printlist` позволяют работать с частичными списками рисунков (`lof` — List of Figures) и таблиц (`lot` — List of Tables). Их синтаксис схож с командами для частичных оглавлений (`\startcontents`, `\stopcontents` и т. д.), но они работают только с `lof` и `lot`.

---

- `\startlist[<name>]{<list>}`

**Описание**:  
Начинает формирование частичного списка (`lof` или `lot`). В `⟨name⟩` указывается имя набора записей (например, `chapters` для списка рисунков в каждой главе). Если `⟨name⟩` не указан, используется `default`.

**Пример**:
`\startlist[chapters]{lof} % Начинаем собирать частичный список рисунков для главы`

С этого момента все добавляемые рисунки будут записываться в данный список.

---

- `\stoplist[<name>]{<list>}`

**Описание**:  
Останавливает сбор записей в частичный список.

---

- `\resumelist[<name>]{<list>}`

**Описание**:  
Возобновляет сбор записей в частичный список после `\stoplist`.

---

- `\printlist[<name>]{<list>}{<prefix>}[<toc-depth>]{<toc-code>}`

**Описание**:  
Выводит частичный список (`lof` или `lot`) с настройками форматирования.  
Отличие от `\printcontents` в том, что здесь нет `start-level`, так как таблицы и рисунки не имеют иерархии уровней.

**Аргументы**:

- `<name>` — Имя набора записей.
- `<list>` — `lof` (рисунки) или `lot` (таблицы).
- `<prefix>` — Префикс для стилей заголовков списка.
- `<toc-depth>` — Глубина записей.
- `<toc-code>` — Дополнительные локальные настройки.

**Пример**:
`\printlist[chapters]{lof}{fig}{}`

Выведет частичный список рисунков `lof` из набора `chapters`, используя стиль `fig`.

---

##### Вставка рисунка в оглавлениеi (`\addtocontents`)

**Описание**:  
Позволяет вставлять специальные элементы (например, рисунки) в оглавление, список рисунков (`lof`) или список таблиц (`lot`). Однако аргументы должны быть защищены `\protect`, иначе могут возникнуть ошибки.

**Пример**:

- Определим команду для вставки рисунка:

```
\newcommand{\figureintoc}[1]{%
  \begin{figure}
    \includegraphics{#1}%
  \end{figure}
}
```

- Добавим рисунок в содержимое:
`\addtocontents{lof}{\protect\figureintoc{myfig}}`

Этот код вставит рисунок `myfig` в список рисунков (`lof`).


