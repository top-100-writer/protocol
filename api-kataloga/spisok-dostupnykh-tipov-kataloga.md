# Список доступных типов каталога

Позволяет получить список типов каталога, к которым у вас есть доступ.

**URL:** `GET /api/partner/v2.0/rating/classifiers/types`

## Параметры запроса <a id="-7"></a>

Запрос вызывается без параметров.

**Пример запроса**

```text
GET /api/partner/v2.0/rating/classifiers/types HTTP/1.1
Accept: */*
Accept-Encoding: gzip, deflate
Authorization: key KtdCzvnscS1U6ovSkvkoY6lAv8nu0mntoyapwrAmhFXSHlGAhmxKb0AFrqo4Qd7Y
Connection: keep-alive
Host: statstand11.top100.rambler.tech:8080
User-Agent: HTTPie/0.9.9
```

## Параметры ответа <a id="-8"></a>

| **Поле** | **Тип** | **Описание** |
| :--- | :--- | :--- |
| result | List\[Classifier\] | Перечень доступных типов каталога. Содержит массив структур &lt;Classifier&gt; \(с вложенными полями, характеризующими каждый из доступных типов\). Описание структуры объекта &lt;Classifier&gt; см. ниже. |

**Структура объекта &lt;Classifier&gt;**

| **Поле** | **Тип** | **Описание** |
| :--- | :--- | :--- |
| id | Int | Идентификатор типа. |
| title | String | Название типа. |

**Пример ответа**

```text
HTTP/1.1 200 OK
Content-Type: application/json
{
    "result": [
        {
            "id": 1,
            "title": "Городские и региональные порталы"
        }
    ]
}
```

