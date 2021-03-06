# Разметка страниц сайта для аналитики блоков

При необходимости можно настроить сбор данных по количеству показов и нажатий на интересующие блоки страниц сайта.

Для этого следует передавать в [запросе в Топ-100](razmetka-stranic-saita-dlya-analitiki-blokov.md) в качестве значения параметра «`bl`» наименования data-атрибутов \(например, `["data-attr1::block1::block2"]`\).

Если событие логически соотносится сразу с несколькими цепочками блоков страницы, то в качестве значения «`bl`» следует передавать сразу весь массив таких цепочек. При этом к данным перед присвоением параметру «`bl`» следует применить `JSON.stringify(<массив цепочек блоков>)`.

Например, если есть набор цепочек блоков: "`data-attr1::block1::block2`", "`data-attr2::block3`", "`data-attr3::block5::block6::block7`", то в качестве «`bl`» надо подставлять `JSON.stringify` от массива `["data-attr1::block1::block2", "data-attr2::block3", "data-attr3::block5::block6::block7"]`.

Накопленная статистика будет доступна для просмотра в отчете «Аналитика блоков»:

* При указании нескольких различных data-атрибутов в отчёте «Аналитика блоков» статистика будет представлена в разрезе нескольких деревьев: название каждого data-атрибута станет первым уровнем дерева в отчёте. Так, например, если необходимо собирать три типа событий: клики по партнёрским блокам, клики по блокам с новостями, клики по панели навигации, то для удобства работы с данными в отчёте можно создать три data-атрибута: `partner`, `news`, `navigation`.
* Для отчёта «Аналитика блоков» собираются только показы блоков и клики по ним. В отчёте также можно увидеть CTR блока. Показы и клики суммируются на каждом уровне дерева размеченных элементов сайта \(осуществляется суммирование по вложенным элементам\). Если же вам важно видеть посетителей и визиты, используйте разметку параметров визита вместо аналитики блоков.

**Пример запроса с передачей параметра bl \(для цепочки из одного блока вида `["data-attr1::block1"]`\) для события клика по блоку \(**`et=cl`**\):**

`http[s]://kraken.rambler.ru/cnt/?et=cl&bl=%5B%22data-attr1%3A%3Ablock1%22%5D&...`

