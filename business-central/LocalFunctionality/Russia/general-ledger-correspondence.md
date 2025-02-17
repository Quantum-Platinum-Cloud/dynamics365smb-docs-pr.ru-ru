---
title: Корреспонденция финансовых операций в России
description: Российские улучшения включают корреспонденцию финансовых операций.
author: DianaMalina
ms.topic: conceptual
ms.search.keywords: null
ms.date: 04/01/2021
ms.reviewer: edupont
ms.author: soalex
---
# <a name="general-ledger-correspondence" />Корреспонденция финансовых операций

Функция корреспонденции финансовых операций позволяет: 

- Периодически создавать транзакцию корреспонденции.
- Учитывать операции корреспонденции при учете финансовых транзакций.
- Анализировать ряд отчетов для корреспонденции.

## <a name="creating-a-general-ledger-correspondence-entry" />Создание операции финансовой корреспонденции

Ниже приводится процедура периодического создания операций финансовой корреспонденции.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](../../media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Создание корреспонденции счетов**, а затем выберите связанную ссылку.
2. Введите в поле **Номер транзакции** номер транзакции, если финансовая корреспонденция должна быть создана только для выбранной транзакции. В противном случае оставьте поле пустым.

Чтобы настроить автоматическую финансовую корреспонденцию:

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](../../media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Настройка ГК**, а затем выберите связанную ссылку.
2. Установите флажок **Авт. корреспонденция**.

## <a name="reports" />Отчеты

Следующие отчеты были добавлены для анализа данных из транзакций корреспонденции:

- Фин. Корресп. Главная Книга (страница 12403; отчет 12431)
- Операции корреспонденции (страница 12401)
- Отчет Фин. Корресп. Журнал-Ордер (отчет 12432)
- Отчет Фин. Корресп. Анализ Операций (отчет 12435)

### <a name="general-ledger---correspondence-window" />Окно "Фин. Корресп. Главная Книга"

Окно **Фин. Корресп. Главная Книга** отображает обороты по корреспонденции счетов за выбранный период.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](../../media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Корреспонденция**, а затем выберите связанную ссылку.
2. Выберите действие **Фин. Корресп. Главная Книга**.

Заголовок окна **Фин. Корресп. Главная Книга** содержит следующие фильтры:

- Фильтр по дате
- Фильтр по филиалу
- Фильтр по глобальному измерению 1
- Фильтр по глобальному измерению 2

В подформе отчета показан оборот в корреспонденции с другими счетами:

:::image type="content" source="../../media/ru/General-Ledger-Correspondence.png" alt-text="Корреспонденция финансовых операций.":::

### <a name="gl-corresp-entries-analysis-report" />Отчет Фин. Корресп. Анализ Операций

**Отчет Фин. Корресп. Анализ Операций** отображает записи корреспонденции для каждого счета. Отчет может использоваться для обзора операций по счету главной книги с корреспондированием и итоговыми суммами.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](../../media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Корреспонденция**, а затем выберите связанную ссылку.
2. Выберите действие **Фин. Корресп. Анализ Операций**.

На вкладке **Параметры** формы запроса имеется возможность задать параметры, заполнив поля сведениями, описанными в следующей таблице.

| Поле                  | Описание                                                  |
| ---------------------- | ------------------------------------------------------------ |
| **Начало периода**   | Введите дату начала периода для операций, которые нужно включить в отчет. |
| **Окончание периода**   | Введите дату окончания периода для операций, которые нужно включить в отчет. |
| **Другие параметры**:<br />**Без нулевых оборотов**, **Без нулевых строк**, **Дебет и кредит раздельно**, **Новая страница для счета ГК** | Указание представления отчета, например, нужно ли выводить сведения для каждого счета без нулевых строк или нулевых оборотов. |

## <a name="see-also" />См. также

[Функциональность локальной версии для России](russia-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
