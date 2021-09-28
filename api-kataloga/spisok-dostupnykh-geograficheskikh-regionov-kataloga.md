# Список доступных географических регионов каталога

Позволяет получить список географических регионов каталога, к которым у вас есть доступ.

**URL:** `GET /api/partner/v2.0/rating/classifiers/regions`

## Параметры запроса <a id="-5"></a>

Запрос вызывается без параметров.

**Пример запроса**

```text
GET /api/partner/v2.0/rating/classifiers/regions HTTP/1.1
Accept: */*
Accept-Encoding: gzip, deflate
Authorization: key qwertyuiop1234567890
Connection: keep-alive
Host: statstand11.top100.rambler.tech:8080
User-Agent: HTTPie/0.9.9
```

## Параметры ответа <a id="-6"></a>

| **Поле** | **Тип** | **Описание** |
| :--- | :--- | :--- |
| result | List\[Classifier\] | Перечень доступных географических регионов каталога. Содержит массив структур &lt;Classifier&gt; \(с вложенными полями, характеризующими каждый из доступных регионов\). Описание структуры объекта &lt;Classifier&gt; см. ниже. |

**Структура объекта &lt;Classifier&gt;**

| **Поле** | **Тип** | **Описание** |
| :--- | :--- | :--- |
| id | Int | Идентификатор региона. |
| title | String | Название региона. |
| parent\_id | Int | Идентификатор родительского региона. |

**Пример ответа**

```text
HTTP/1.1 200 OK
Content-Type: application/json
{
    "result": [
        {
            "id": 1,
            "parent_id": 0,
            "title": "Россия"
        }
    ]
}
```

