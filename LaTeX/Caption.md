#### Пользовательские команды

**Коротко:**

- `\caption{}` — стандартная подпись.
- `\caption*{}` — без номера и без записи в список.
- `\captionof{}` — подпись вне `figure`/`table`.
- `\captionof*{}` — подпись без номера вне `figure`/`table`.

---

- `\caption[<list entry>]{<heading>}` — Основная команда для создания подписи.

**Где:**

- `<list entry>` — опциональный аргумент, предназначенный для использования в списке рисунков или таблиц (table of figures/tables). Обычно содержит краткое описание, отличное от полного текста подписи.
- `<heading>` — обязательный аргумент, содержащий текст подписи.

---

- `\caption*{<heading>}` — Команда для создания подписи без номера.



---

- `\captionof{<float type>}[<list entry>]{<heading>}`

Команда для создания подписи к объекту, который не является стандартным плавающим объектом (например, к объекту, созданному с помощью другого пакета).

- `<float type>` — обязательный аргумент, указывающий тип объекта, к которому добавляется подпись (например, `figure`, `table`, `listing`).
- `<list entry>` — опциональный аргумент, аналогичный `<list entry>` в команде `\caption`.
- `<heading>` — обязательный аргумент, содержащий текст подписи.

---

- `\captionof*{<float type>}{<heading>}`

Команда для создания подписи без номера к объекту, который не является стандартным плавающим объектом.

---

**Основная команда настройки подписей:**

`\captionsetup[<float type>]{<options>}`

**Синтаксис:**

- `<float type>` — тип плавающего объекта (`figure`, `table` и др.).
- `<options>` — список опций, разделённых запятыми, которые настраивают стиль подписи.

**Пример использования:**
`\captionsetup[figure]{format=hang, indention=0.5cm, labelformat=parens}`

Настроит формат подписей для рисунков: висячий отступ (`hang`), отступ второго и последующих строк `0.5cm`, а номер подписи будет в скобках.

---

#### Опции

- `format` — задаёт формат подписи

Опция определяет, как отображается подпись (метка + текст).

**Доступные значения:**

- `plain` — обычный абзац.
- `hang` — текст смещается так, что второй и последующие строки имеют отступ.

---

- `indention=<размер>` — отступ после первой строки

Используется для смещения текста подписей.

---

- `labelformat` — формат метки (название + номер)

Определяет, как будет выглядеть метка (например, "Рисунок 1" или "(1)").

**Доступные значения:**

- `original` — формат, заданный классом документа.
- `empty` — убирает метку.
- `simple` — стандартный формат (название + номер).
- `brace` — номер в фигурных скобках `{}`.
- `parens` — номер в круглых скобках `()`.

---

- `labelsep` — разделитель между меткой и текстом подписи

Определяет, какой символ будет между "Рисунок 1" и самим текстом.

**Доступные значения:**

- `none` — без разделителя.
- `colon` — двоеточие с пробелом (`Рисунок 1: Описание`).
- `period` — точка с пробелом (`Рисунок 1. Описание`).
- `space` — один пробел (`Рисунок 1 Описание`).
- `quad` — `\quad` между меткой и текстом.
- `newline` — разрыв строки (`\\`).
- `endash` — короткое тире (`Рисунок 1 -- Описание`).

---

- `textformat` — форматирование текста подписи

Определяет, как будет выглядеть сам текст.

**Доступные значения:**

- `empty` — убирает текст подписи.
- `simple` — текст без изменений.
- `period` — текст оканчивается точкой.

**Пример:**
`\captionsetup{textformat=period} % "Рисунок 1. Описание."`

---

- `justification` — определяет выравнивание подписей.

Доступные варианты:

- `justified` — обычное выравнивание по ширине.
- `centering` — выравнивание по центру.
- `centerlast` — только последняя строка выравнивается по центру.
- `centerfirst` — только первая строка по центру.
- `raggedright` — выравнивание по левому краю (без переносов).
- `RaggedRight` — как `raggedright`, но с переносами (из пакета `ragged2e`).
- `raggedleft` — выравнивание по правому краю.

---

- `singlelinecheck` — Определяет, нужно ли центрировать подписи, состоящие из одной строки.

Доступные варианты:

- `true` (по умолчанию) — если подпись короткая, она центрируется.
- `false` — отключает автоматическое центрирование.

---

#### Настройка шрифтов

- `font=<font options>` — определяет шрифт всей подписи.
- `labelfont=<font options>` — определяет шрифт только для метки и разделителя (Figure 1).
- `textfont=<font options>` — определяет шрифт только для текста подписи.

**Доступные опции:**

- `scriptsize` — очень маленький.
- `footnotesize` — размер сноски.
- `small` — мелкий.
- `normalsize` — обычный размер.
- `large`, `Large` — увеличенные размеры.
- `bf` — жирный (`\bfseries` эквивалент).
- `it` — курсив (`\itshape` эквивалент).
- `sl` — наклонный (`slshape` эквивалент).
- `sc` — капитель (`\scshape` эквивалент).
- `rm` — шрифт с засечками (`\rmfamily` эквивалент).
- `sf` — без засечек (`\sffamily` эквивалент).
- `tt` — моноширинный (`\ttfamily` эквивалент).
- `color=<цвет>` — изменение цвета, если загружен пакет `color` или `xcolor`.
- `singlespacing`, `onehalfspacing`, `doublespacing` — межстрочный интервал.
- `stretch=<amount>` — задать точный межстрочный интервал.

---

- `margin` и `width` — эти опции позволяют задать дополнительные отступы или фиксированную ширину для подписей.

**Синтаксис:**
```
margin=<amount>
margin={<left amount>,<right amount>}
width=<amount>
```

- `margin=10pt` — одинаковый отступ слева и справа по 10pt.
- `margin={1cm,0cm}` — слева 1cm, справа 0cm.
- `width=.75\textwidth` — фиксированная ширина подписи 75% от ширины текста.

При двухсторонней верстке (`twoside`) отступы меняются местами на четных страницах. Чтобы этого избежать, можно добавить `oneside`.

**Дополнительные параметры:**

- `margin*=` — изменяет отступ только если не задана ширина (`width`).
- `minmargin=⟨amount⟩` — минимальный отступ.
- `maxmargin=⟨amount⟩` — максимальный отступ.

---

- `parskip=<amount>` — задает вертикальный интервал между абзацами в подписи.

---

- `hangindent=<amount>` — задает выступающий абзац (hanging indent), начиная со второй строки каждого абзаца.

**Пример:**
`hangindent=-0.5cm`

Вторая и последующие строки каждого абзаца будут сдвинуты влево на 0.5см.

---

- `skip=<amount>` — определяет вертикальный интервал между подписью (`\caption`) и содержимым таблицы/рисунка.

---

- `position=<key>` — определяет, где размещается подпись относительно содержимого.

**Ключи:**
- `top` или `above` — подпись предполагается сверху, интервал (`skip`) будет добавляться снизу.
- `bottom` или `below` — подпись предполагается снизу, интервал (`skip`) будет добавляться сверху.
- `auto` (по умолчанию) — пакет пытается сам определить положение подписи.

>**Важно:** `position=top` **не перемещает** подпись автоматически вверх! Оно лишь определяет, как должен работать `skip`.

---

- `figureposition` и `tableposition`

Определяют положение подписи только для рисунков (`figure`) или таблиц (`table`).

**Синтаксис:**
```
figureposition=top | bottom | auto
tableposition=above | below | auto
```

- `figureposition=top` — все подписи в `figure` будут рассматриваться как верхние.
- `tableposition=above` — все подписи в `table` будут рассматриваться как верхние.

---

- `list=yes | no` — определяет, добавляется ли подпись в список рисунков (`LoF`) или список таблиц (`LoT`).

---

- `listformat` — определяет, как номер рисунка/таблицы будет оформляться в `LoF` и `LoT`.

Доступные значения:

- `empty` — номер не будет отображаться.
- `simple` — номер с префиксом (например, "Рис. 1").
- `parens` — номер в скобках (например, "(1)").
- `subsimple` — как `simple`, но без префикса.
- `subparens` — как `parens`, но без префикса.

---

- `name=<новое имя>` — позволяет переопределить название подписи (например, вместо "Figure" использовать "Рис.").

Полезно для изменения подписи в отдельных окружениях (`wrapfigure`, `table`, `figure` и т. д.).

**Пример:**
```
\captionsetup[figure]{name=Рис.} % Все подписи к рисункам станут "Рис."
\captionsetup[table]{name=Табл.} % Все подписи к таблицам станут "Табл."
```

---

- `type=<float type>`

Используется, чтобы явно указать, к какому типу (`figure` или `table`) относится подпись в нестандартных окружениях (например, `minipage`).

**Пример:**
```
\begin{minipage}{0.5\textwidth}
    \captionsetup{type=figure}
    \includegraphics[width=\linewidth]{image.png}
    \caption{Описание рисунка}
\end{minipage}
```

**Дополнительная опция**: `type*=<float type>`

Работает так же, но не создаёт гиперссылку при использовании `hyperref`.
