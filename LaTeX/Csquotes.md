`\command*{}`: Команды с звездочкой указывают использовать внутренние кавычки.

---

- `\enquote{text}`: Выводит текст в кавычках, выбранных в соответствии с текущим языком документа.
- `\foreignquote{lang}{text}`: Цитирует текст с учетом правил языка `lang`.
- `\hyphenquote{lang}{text}`: Меняет только правила переноса для языка.
---
- `\textquote[cite][punct]{text}⟨tpunct⟩`:
  **Параметры:**
  `[cite]`: Источник цитаты. Может быть именем автора, названием книги или другим указанием на источник.
  `[punct]`: Пунктуация перед закрывающей кавычкой.
  `⟨tpunct⟩`: Пунктуация после закрывающей кавычки.
- `\foreigntextquote{lang}[cite][punct]{text}⟨tpunct⟩`: 
  Аналогично `\textquote`, но для цитат на иностранном языке.
- `\hyphentextquote{lang}[cite][punct]{text}⟨tpunct⟩`: Меняет только правила переноса для языка.
---
- `\blockquote[cite][punct]{text}⟨tpunct⟩`: Выводит текст в виде блочной цитаты.
- `\foreignblockquote{lang}[cite][punct]{text}⟨tpunct⟩`: 
  Аналогично `\blockquote`, но для цитат на иностранном языке.
- `\hyphenblockquote{lang}[cite][punct]{text}⟨tpunct⟩`: Меняет только правила переноса для языка.
- `\hybridblockquote{lang}[cite][punct]{text}⟨tpunct⟩`: Эта команда ведет себя как `\hyphenquote`, если цитата короткая. Если она превышает порог, команда ведет себя как `\foreignblockquote`.
---

- `\textcquote[prenote][postnote]{key}[punct]{text}⟨tpunct⟩`:
  **Параметры:**
  `[prenote]`: Текст, который выводится перед источником.
  `[postnote]`: Текст, который выводится после источника.
  `{key}`: Ключ, который ссылается на запись в библиографической базе данных.
- `\foreigntextcquote{lang}[prenote][postnote]{key}[punct]{text}⟨tpunct⟩`: Аналогично `\textcquote`, но для цитат на иностранном языке.
- `\hyphentextcquote{lang}[prenote][postnote]{key}[punct]{text}⟨tpunct⟩`: Меняет только правила переноса для языка.
---
- `\blockcquote[prenote][postnote]{key}[punct]{text}⟨tpunct⟩`: Выводит текст в виде блочной цитаты.
- `\foreignblockcquote{lang}[prenote][postnote]{key}[punct]{text}⟨tpunct⟩`: Аналогично `\blockcquote`, но для цитат на иностранном языке.
- `\hyphenblockcquote{lang}[prenote][postnote]{key}[punct]{text}⟨tpunct⟩`: Меняет только правила переноса для языка.
- `\hybridblockcquote{lang}[prenote][postnote]{key}[punct]{text}⟨tpunct⟩`: Эта команда ведет себя как `\hyphenblockcquote`, если цитата короткая, и как `\foreignblockquote`, если она длинная.

---

- `\textelp{}`: Команда для обозначения пропуска текста в цитате.
  **Пример:**
  ```
	\textelp{} = [...]
	\textelp{text} = [...][text]
	\textelp*{text} = [text] [...]
	```

- `\textins{text}`: Команда для обозначения вставленного текста в цитату.
  **Пример:**
  ```
	\textins{text} = [text]
	\textins*{T}ext = [T]ext
	```
	
- `\textdel{text}`: Команда для обозначения удаленного текста из цитаты.
  **Пример:**
  ```
	text\textdel{s} = text[]
	```

### Среды отображения

```
\begin{displayquote}[cite][punct]
...
\end{displayquote}
```

---
```
\begin{foreigndisplayquote}{lang}[cite][punct]
...
\end{foreigndisplayquote}
```

---
```
\begin{hyphendisplayquote}{lang}[cite][punct]
...
\end{hyphendisplayquote}
```

---
```
\begin{displaycquote}[prenote][postnote]{key}[punct]
...
\end{displaycquote}
```

---
```
\begin{foreigndisplaycquote}{lang}[prenote][postnote]{key}[punct]
...
\end{foreigndisplaycquote}
```

---
```
\begin{hyphendisplaycquote}{lang}[prenote][postnote]{key}[punct]
...
\end{hyphendisplaycquote}
```

### Настройки и переопределения

**Эта команда служит для определения нового стиля кавычек:**

```
\DeclareQuoteStyle[variant]{style}[outer init][inner init]%
	{opening outer mark}[middle outer mark]{closing outer mark}[kern]%
	{opening inner mark}[middle inner mark]{closing inner mark}
```

**Объяснение:**

- `[variant]`: Указывает вариант стиля.
- `{style}`: Имя нового стиля.
- `[outer init]`: Код, выполняемый _перед_ выводом внешних кавычек. Может быть полезен для настройки шрифта, размера и т.д.
- `[inner init]`: Код, выполняемый _перед_ выводом внутренних кавычек (для вложенных цитат).
- `{opening outer mark}`: Символ или команда, используемая для _открывающей_ внешней кавычки.
- `[middle outer mark]`: Символ или команда для _средней_ внешней кавычки (используется, например, в некоторых языках для обозначения цитат внутри цитат).
- `{closing outer mark}`: Символ или команда для _закрывающей_ внешней кавычки.
- `[kern]`: Величина кернинга (расстояния) между внешними и внутренними кавычками.
- `{opening inner mark}`: Символ или команда для _открывающей_ внутренней кавычки.
- `[middle inner mark]`: Символ или команда для _средней_ внутренней кавычки.
- `{closing inner mark}`: Символ или команда для _закрывающей_ внутренней кавычки.

---
- `\setquotestyle{style}`: Установить стиль кавычек.
- `\ExecuteQuoteOptions{key=value, ...}`: Установка параметров для пакета.


| Функция      | Опция               | Описание                                                                                                                                                                                             |
| ------------ | ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `strict`     | `true, false`       | Превращает все предупреждения пакета в сообщения об ошибках.                                                                                                                                         |
| `style`      | `⟨style⟩`           | Выбирает фиксированный стиль цитирования.                                                                                                                                                            |
| `autostyle`  | `true, false, once` | Управляет многоязыковой поддержкой. `true` постоянно адаптирует стиль цитаты к текущему языку документа; `once` адаптирует стиль только один раз, чтобы он соответствовал основному языку документа. |
| `⟨language⟩` | `⟨variant⟩`         | Используйте параметры языка, чтобы выбрать вариант стиля, если их несколько для определенного языка.                                                                                                 |
