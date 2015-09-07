# rouble-test
Мини-проект для тестирования шрифтов из библиотеки Гугл.Фонтс.

## Протокол испытаний:
- шрифт подключается способом рекомендованным серисом Гугл.Фонтс
- по умолчанию используется subset=cyrillic,latin и font-weight: 400; для подробной проверки интересных кадидатов добавляются дополнительные font-weight
- знак рубля вставляется в текст юникодным символом (вводится с клавиатуры, при включенном русском языке: alt + «р» == ₽); кодировка страницы charset=utf-8
- страница на ГитХаб.Пейджес открывается в браузерах последних версий на системах со всеми установленными обновлениями
- в тестировании участвуют: Виндоус 10, МакОС Икс и Убунту; ИЕ, Хром, Файерфокс, Опера и Яндекс.Браузер
- рендер в каждом случае проверяется визуально и в инспекторе элементов (сегмент Rendered Fonts вкладки Computed показывает количество использованных глифов и названия использованных шрифтов)

## Результаты (07.09.2015)
- ПТ Санс — _единственный_ из шрифтов Гугл.Фонтс, в котором ₽ входит в набор глифов и отображается на Виндоус и Мак
- все остальные шрифты не содержат специального символа рубля
- вместо отстутствующего глифа система/браузер подставляют подходящий глиф из наиболее подходящего по их мнению шрифта
- Видноус в подстановке используется Ариал и Тахома (в ФайерФоксе еще и Таймс Нью Роман), в зависимости от насыщенности «обезрубленного» шрифта
- МакОС Икс в подстановке использует Гельветику
- Ариал и Тахома — в Виндоус содержат знак рубля, он выводится в ИЕ, Файерфоксе, Хроме, Опере но не выводится в Яндекс.Браузере
- Таймс Нью Роман содержит соответствующий глиф, знак рубля в заголовке, набранном Таймс Нью Роман, выводится в Виндоус во всех браузерах
- Гельветика содержит знак рубля

{todo}
- подробнее описать результаты на МакОС ИКС
- собрать статистику на Убунту
- свести результаты в таблицу(?)