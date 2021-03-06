# Передача идентификатора пользователя

Для сбора статистики в разрезе пользователей необходимо присвоить пользователям уникальные идентификаторы и включать их в данные, отправляемые в счетчик Топ-100. Это позволит соотносить в Топ-100 активности на сайте \(просмотры, клики и т.п.\) с заданными пользователями.

Значение идентификатора пользователя user\_id указывается в настройках счётчика при инициализации. При необходимости оно может быть переопределено. Для этого необходимо передать в [запросе в Топ-100](peredacha-identifikatora-polzovatelya.md) в качестве значения параметра «`uid`» новый идентификатор пользователя.

**Пример передачи идентификатора пользователя**`uid=a1234b` **и указанием типа события** `et`**:**

`http[s]://kraken.rambler.ru/cnt/?et=uid&uid=a1234b&...`

Если пользователь не идентифицирован \(разлогинен\), то передавать параметр «`uid`» в [запросе в Топ-100](peredacha-identifikatora-polzovatelya.md) не надо.

