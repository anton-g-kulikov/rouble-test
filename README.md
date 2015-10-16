# rouble-test
Мини-проект для тестирования шрифтов из библиотеки Гугл.Фонтс.

[http://anton-g-kulikov.github.io/rouble-test/](http://anton-g-kulikov.github.io/rouble-test/)

## Протокол испытаний:
- шрифт подключается способом, рекомендованным сервисом
- по умолчанию используется subset=latin,cyrillic,latin-ext и font-weight: 400; для подробной проверки интересных кадидатов добавляются дополнительные font-weight
- знак рубля вставляется в текст юникодным символом; кодировка страницы charset=utf-8
- страница на ГитХаб.Пейджес открывается в браузерах последних версий на системах со всеми установленными обновлениями
- в тестировании участвуют: Виндоус 10, МакОС Икс и Убунту; ИЕ, Хром, Файерфокс, Опера и Яндекс.Браузер
- рендер в каждом случае проверяется визуально и в инспекторе элементов: сегмент Rendered Fonts вкладки Computed показывает количество использованных глифов и названия использованных шрифтов
— все шрифты (кроме «системных») в инспекторе отображаются с пометкой «удаленный» и явной ссылкой вида https://fonts.gstatic.com/{путь}.{формат}


## Результаты (24.09.2015)
### Общие
- вместо отстутствующего глифа система/браузер _подставляют_ подходящий глиф из наиболее подходящего по их мнению шрифта
— в качестве общего хака: чтобы предотвратить использоваение локальных копий или стандартного подстановочного шрифта нужно указать в качестве локального истончика несуществующую гарнитуру и в остальных определениях четко обозначит шрифт и его источник

### Виндоус
- ПТ Санс, Робото и Исток Веб — показывают ₽ в Хроме, Опере и Яндекс.Браузере, ИЕ, и в _Файерфоксе_ при подключении __subset=latin-ext__
- для остальных шрифтов Видноус подставляет вместо знака Ариал (или Тахому, в ФайерФоксе еще и Таймс Нью Роман, в зависимости от насыщенности «обезрубленного» шрифта)
- Ариал и Тахома — в Виндоус содержат знак рубля, он выводится в ИЕ, Файерфоксе, Хроме, Опере; Бета Яндекс.Браузера показывает ₽ только в Тахоме, стабильный - во всех.
- Знак рубля в заголовке, набранном Таймс Нью Роман, выводится в Виндоус во всех браузерах

### МакОС Икс
- МакОС Икс в подстановке использует .Helvetica Neue DeskInterface (в Сафари и Хроме); Гельветика содержит знак рубля
- Таймс на МакОС Икс не содержит знака рубля
- Файерфокс на МакОС Икс не использует для подстановки Гельветику, нужно явно указывать Helvetica Neue
— Локальная копия шрифта Робото в _Файерфоксе_ не показывает знак рубля, при подключении из CDN — все в порядке 
- ПТ Санс и Исток Веб — показывают знак рубля во всех браузерах

{todo}
- собрать статистику на Убунту
- собрать статистику на мобильных ОС/браузерах
- свести результаты в таблицу(?)