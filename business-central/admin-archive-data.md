---
title: Расширение архива данных
description: Архивирование данных создает недорогую резервную копию ваших записей.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bknudsen
ms.topic: conceptual
ms.date: 01/30/2023
ms.custom: bap-template
ms.search.form: 630
---

# <a name="the-data-archive-extension" />Расширение архива данных

Со временем в вашем бизнесе будет накапливаться значительный объем данных, и вам как администратору, вероятно, потребуется создать стратегию архивирования данных. Наличие большого количества данных может замедлить работу, например, может потребоваться немного больше времени для создания отчетов или даже блокировки записей. Кроме того, большие объемы данных могут привести к увеличению затрат на хранение.

Расширение архива данных обеспечивает базовую структуру для архивирования и резервного копирования данных в рамках сжатия данных. Сжатие по дате объединяет связанные записи объединяются в одну запись, а оригиналы удаляются. Подробнее см. в разделе [Сжатие данных с помощью сжатия по дате](admin-manage-documents.md#compress-data-with-date-compression). Однако сохранение этих данных может иметь значение, поэтому вместо их удаления вы можете заархивировать их для дальнейшего использования.

## <a name="start-archiving-data" />Начать архивирование данных

Расширение предустановлено и доступно в **Управление расширениями**, поэтому для начала ничего делать не нужно. Расширение также доступно в AppSource.

Ваши архивы данных перечислены на странице **Список архивов данных**. Каждый архив может содержать данные из нескольких таблиц и может содержать до 10 000 записей. Если в таблице более 10 000 записей, будет создан второй архив для следующих 10 000 записей и так далее. Например, если вы заархивируете 10 100 записей главной книги, Business Central создаст один архив «Запись ГК» для первых 10 000 записей, а затем второй архив для оставшихся 100 записей.

После архивирования данных вы можете изучить их, используя Microsoft Excel или файл CSV.

* Если вы используете вариант Excel, рабочая книга будет содержать по одному листу для каждой таблицы архива данных.
* Если вы используете вариант CSV, вы получите ZIP-файл с одним CSV-файлом для каждой таблицы архива данных.

> [!TIP]
> Параметры Excel и CSV упрощают использование другого приложения или службы для перемещения данных в другое место, например в хранилище BLOB-объектов Azure или в инструмент анализа, например Microsoft Power BI.

Расширение архива данных используются следующими пакетными заданиями для сжатия данных.

|Пакетные задания  |
|---------|
|Сжатие данных Операции товарного бюджета |
|Сжатие по дате — книга операций по банку/кассе |
|Сжатие по дате - книга клиентов |
|Сжатие по дате - книга ОС |
|Сжатие по дате - Главная книга |
|Сжатие по дате - книга страхования |
|Сжатие по дате - книга обслуж. |
|Сжатие по дате - книга обслуж. |
|Сжатие по дате - книга ресурсов |
|Сжатие по дате - операции НДС |
|Сжатие по дате - книга поставщиков |
|Сжатие по дате - складские Операции |
|Сжатие данных Операции бюджета ГК |

Чтобы начать архивирование данных при запуске одного из пакетных заданий, включите переключатель **Архивировать удаленные операции**.

## <a name="storage-considerations" />Рекомендации по хранению

Архивные данные хранятся в таблице **Мультимедиа арендатора**. Мы рекомендуем экспортировать старые архивы, например, в файл CSV, а затем удалить старые архивные записи.

## <a name="see-also" />См. также

[Управление хранилищем путем удаления документов или сжатия данных](admin-manage-documents.md)
