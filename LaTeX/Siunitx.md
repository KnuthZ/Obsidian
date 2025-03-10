### Основные команды

`.` и `~` — межъединичное произведение.
#### Номера

`\num[options]{number}`: Форматирует числовые данные, автоматически добавляя разделители тысячных и обрабатывая научную запись.
**Пример:**
`\num{12345.678}` — $12\:345.678$
`\num{1.23e4}` — $1.23 \times 10^4$
`\num{-e10}` — $-10^{10}$

---

`\numlist[options]{numbers}`: Форматирует список чисел, разделенных точкой с запятой.
**Пример:**
`\numlist{10;30;50;70}` — $10, 30, 50\ \text{and}\ 70$

---

`\numproduct[options]{numbers}`: Отображает произведение чисел.
**Пример:**
`\numproduct{10 x 30}` — $10\times 30$

---

`\numrange[options]{number1}{number2}`: Форматирует числовой диапазон.
**Пример:**
`\numrange{10}{30}` — $10\ \text{to}\ 30$

#### Углы

`\ang[options]{angle}`: Отображает угол с соответствующим символом для градусов, минут и секунд.
**Пример:**
`\ang{10}` — $10^\circ$
`\ang{1;2;3}` — $1^\circ\, 2'\, 3''$
`\ang{;;1}` — $1''$
#### Единицы

`\unit[options]{unit}`: Отображает единицы измерения с форматированием.
**Пример:**
`\unit{kg.m/s^2}` — $\text{kg m/s}^2$
`\unit{g_{polymer}~mol_{cat}.s^{-1}}` — $\text{g}_{\text{polymer}}\:\text{mol}_{\text{cat}}\:\text{s}^{-1}$

**Основные параметры:**
- `\per`: Минус в степени и разделитель для дробных величин.
- `\square\command`: Возвести в квадрат. 
- `\cubic\command`: Возвести в куб. 

---

`\qty[options]{number}{unit}`: Комбинирует числовое значение и единицу измерения.
**Пример:**
`\qty[mode = text]{1.23}{J.mol^{-1}.K^{-1}}` — $1.23\:\text{J mol}^{-1}\: \text{K}^{-1}$
`\qty{.23e7}{\candela}` — $0.23\times 10^7\: \text{cd}$
`\qty[per-mode = symbol]{1.99}{\per\kilogram}` — $1.99/\text{kg}$
`\qty[per-mode = fraction]{1,345}{\coulomb\per\mole}` — $1.345\frac{\text{C}}{\text{mol}}$

---

`\qtylist[options]{numbers}{unit}`: Список чисел с общей единицей измерения.
**Пример**:
`\qtylist{10;30;45}{\metre}` — $10\:\text{m,}\ 30\:\text{m and}\ 45\:\text{m}$

---

`\qtyproduct[options]{numbers}{unit}`: Произведение чисел с единицей измерения.
**Пример**:
`\qtyproduct{10 x 30 x 45}{\metre}` — $10\:\text{m} \times 30\:\text{m} \times 45\:\text{m}$

---

`\qtyrange[options]{number1}{number2}{unit}`: Диапазон значений с единицей измерения.
**Пример**:
`\qtyrange{10}{30}{\metre}` — $10\:\text{m to}\ 30\:\text{m}$

### Опции

| Единица                  | Команда             | Символ           |
| ------------------------ | ------------------- | ---------------- |
| Ампер                    | `\ampere`           | $\text{A}$       |
| Кандела                  | `\candela`          | $\text{cd}$      |
| Кельвин                  | `\kelvin`           | $\text{K}$       |
| Килограмм                | `\kilogram`         | $\text{kg}$      |
| Метр                     | `\metre`            | $\text{m}$       |
| Моль                     | `\mole`             | $\text{mol}$     |
| Секунда                  | `\second`           | $\text{s}$       |
| Беккерель                | `\becquerel`        | $\text{Bq}$      |
| Градус Цельсия           | `\degreeCelsius`    | $^\circ\text{C}$ |
| Кулон                    | `\coulomb`          | $\text{C}$       |
| Фарад                    | `\farad`            | $\text{F}$       |
| Грей                     | `\gray`             | $\text{Gy}$      |
| Герц                     | `\hertz`            | $\text{Hz}$      |
| Генри                    | `\henry`            | $\text{H}$       |
| Джоуль                   | `\joule`            | $\text{J}$       |
| Люмен                    | `\lumen`            | $\text{lm}$      |
| Катал                    | `\katal`            | $\text{kat}$     |
| Люкс                     | `\lux`              | $\text{lx}$      |
| Ньютон                   | `\newton`           | $\text{N}$       |
| Ом                       | `\ohm`              | $\Omega$         |
| Паскаль                  | `\pascal`           | $\text{Pa}$      |
| Радиан                   | `\radian`           | $\text{rad}$     |
| Сименс                   | `\siemens`          | $\text{S}$       |
| Зиверт                   | `\sievert`          | $\text{Sv}$      |
| Стерадиан                | `\steradian`        | $\text{sr}$      |
| Тесла                    | `\tesla`            | $\text{T}$       |
| Вольт                    | `\volt`             | $\text{V}$       |
| Ватт                     | `\watt`             | $\text{W}$       |
| Вебер                    | `\weber`            | $\text{Wb}$      |
| астрономическая единица  | `\astronomicalunit` | $\text{au}$      |
| Бел                      | `\bel`              | $\text{B}$       |
| Дальтон                  | `\dalton`           | $\text{Da}$      |
| День                     | `\day`              | $\text{d}$       |
| Децибел                  | `\decibel`          | $\text{dB}$      |
| Градус                   | `\degree`           | $^\circ$         |
| Электронвольт            | `\electronvolt`     | $\text{eV}$      |
| Гектар                   | `\hectare`          | $\text{ha}$      |
| Час                      | `\hour`             | $\text{h}$       |
| Литр                     | `\litre`            | $\text{L}$       |
| Минута (угол плоскости)  | `\arcminute`        | $'$              |
| Минута (время)           | `\minute`           | $\text{min}$     |
| Секунда (угол плоскости) | `\arcsecond`        | $''$             |
| Непер                    | `\neper`            | $\text{Np}$      |
| Тонна                    | `\tonne`            | $\text{t}$       |
| Килограмм                | `\kg`               | $\text{kg}$      |
| Миллисекунда             | `\ms`               | $\text{ms}$      |


