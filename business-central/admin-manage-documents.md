---
title: Управление хранилищем путем удаления документов или сжатия данных
description: 'Узнайте, как работать с накоплением исторических документов (и уменьшить объем данных, хранящихся в базе данных), удаляя или сжимая их.'
author: edupont04
ms.topic: conceptual
ms.search.form: '107, 9035, 9040'
ms.date: 09/14/2022
ms.author: edupont
---
# <a name="manage-storage-by-deleting-documents-or-compressing-data" />Управление хранилищем путем удаления документов или сжатия данных

Исполнителю главной роли, например администратору приложения, приходится постоянно иметь дело с накапливающимися архивными документами (удалять или сжимать их).  

> [!TIP]
> О других способах уменьшения объема данных, хранящихся в базе данных, см. в статье [Сокращение объема данных, хранящихся в базах данных Business Central](/dynamics365/business-central/dev-itpro/administration/database-reduce-data) в нашей документации для разработчиков и ИТ-специалистов.

## <a name="delete-documents" />Удаление документов

В определенных ситуациях может возникнуть потребность в удалении заказов на покупку, по которым были выставлены счета. Тем не менее удалить их невозможно, если вам не выставили счета на всю сумму заказа на продажу и вы не получили все товары в нем. [!INCLUDE[prod_short](includes/prod_short.md)] автоматически это проверяет.

Заказы на возврат обычно удаляются после выставления по ним счета. Когда счет учтен, он переносится на страницу **Учтенная кредит-нота покупки**. Если установлен флажок **Создавать возвр. расх. накл. с кредит-нотой** на странице **Настройка модуля "Покупки"**, счет переносится на страницу **Учтенная возвратная расходная накладная**. Можно удалить документы с помощью пакетного задания **Удаление занесенных на счет возвратов покупки**. Перед удалением пакетное задание проверяет, полностью ли отгружены заказы на возврат покупки и выставлены ли по ним счета.  

Общие заказы на покупку не удаляются автоматически после обработки и выставления счетов по всем связанным заказам на покупку. Удалить подобные заказы можно с помощью пакетного задания **Удалить общие заказы на покупку, по которым выставлены счета**.  

Сервисные заказы, по которым выставлены счета, обычно удаляются автоматически после выставления по ним счетов в полном объеме. Во время учета счета на странице **Учтенные сервисные счета** создается соответствующая операция, которую затем там же можно просмотреть.  

Однако сервисные заказы не удаляются автоматически, если общее количество по заказу было учтено не из самого заказа, а со страницы **Сервисный счет**. Такие заказы с выставленными счетами может потребоваться удалить вручную, запустив пакетное задание **Удалить заказы на услуги, для которых выставлены счета**.  

## <a name="compress-data-with-date-compression" />Сжатие данных с помощью сжатия по дате

Вы можете сжать данные в [!INCLUDE [prod_short](includes/prod_short.md)], чтобы сэкономить место в базе данных &mdash; что в [!INCLUDE [prod_short](includes/prod_short.md)] Online может даже сэкономить вам деньги. В пноцессе сжатия, основанного на датах и фукнцих, несколько старых операций объединяется в одну новую.

Можно сжимать операции, которые соответствуют всем из перечисленных ниже условий:

* Они из закрытых финансовых лет.
* Поле **Открыто** имеет значение **Нет**.
* Им как минимум пять лет. Если вы хотите сжать данные, которым меньше пяти лет, обратитесь к своему партнеру Майкрософт.

Например, операции книги поставщиков за предыдущие финансовые годы могут быть сжаты до одной кредитовой и дебетовой операции в месяц. Сумма в новой операции равна общей сумме всех компрессированных операций. Указываемая дата является начальной датой сжимаемого периода, например, первый день месяца (если операции сжимаются по месяцам). После сжатия продолжает отображаться оборот по каждому счету за предыдущий финансовый год.

Количество операций, которые получаются после компрессии даты, зависит от количества установленных фильтров, объединяемых полей и длины выбранного периода. В любом случае создается по меньшей мере одна операция. После завершения пакетного задания его результат можно просмотреть на странице **Регистры сжатия**.

Вы можете сжимать следующие типы данных с использованием пакетных заданий.

* Финансовые операции — операции главной книги (ГК), операции по налогу на добавленную стоимость (НДС), операции книги банковских счетов, операции бюджета ГК, операции книги клиентов и операции книги поставщиков.
* Складские операции
* Записи о ресурсах
* Операции товарного бюджета
* Операции книги основных средств (ОК), операции книги обслуживания ОС и операции книги страхования ОС.

При определении критериев для сжатия вы можете использовать параметры в разделе **Сохранить содержимое полей**, чтобы сохранить содержимое определенных полей. Доступные поля зависят от данных, которые вы сжимаете.

> [!NOTE]
> Чтобы вы могли запустить сжатие данных, ваши аналитические представления должны быть актуальными. Подробнее см. в разделе [Обновление аналитического отчета](bi-how-analyze-data-dimension.md#update-an-analysis-view).

После сжатия всегда сохраняется содержимое следующих полей: **Дата учета**, **Код поставщика**, **Тип документа**, **Код валюты**, **Учетная группа**, **Сумма**, **Сумма остатка**, **Исход. сумма (МВ)**, **Сумма остатка (МВ)**, **Сумма (МВ)**, **Покупка (МВ)**, **Скидка счета (МВ)**, **Скидка оплаты выдана (МВ)** и **Возможная скидка оплаты**.

## <a name="posting-compressed-entries" />Учет сжатых операций

Сжатые записи разносятся немного иначе, чем стандартные. Это сделано для уменьшения количества новых записей в главной книге, создаваемых сжатием по дате, и особенно важно, когда вы храните такую информацию, как аналитики и номера документов. Сжатие по дате создает новые записи следующим образом:

* На странице **Операции главной книги** создаются новые операции для сжатых операций. В поле **Описание** содержится текст **Со сжатием по дате**, так что сжатые записи легко идентифицировать. 
* На страницах книг учета, таких как страница **Книга операций по клиентам**, создается одна или несколько новых операций. 

Процесс разноски создает пропуски в серии номеров для записей на странице **Операции главной книги**. Эти номера присваиваются только записям на страницах главной книги. Диапазон номеров, назначаемых операциям, доступен на странице **Регистр ГК** в полях **От номера операции** и **До номера операции**. 

> [!NOTE]
> После запуска сжатия данных все счета в бухгалтерской книге блокируются. Это означает, что вы не можете, например, сторнировать операции книги постащиков или книги банковских счетов для счетов, затронутых сжатием.

Количество операций, образующихся в результате сжатия по дате, зависит от установленных фильтров, объединяемых полей и длины выбранного периода. В любом случае создается по меньшей мере одна операция.

> [!WARNING]
> Компрессия данных удаляет записи, поэтому следует всегда сохранять резервную копию данных перед запуском пакетного задания.

### <a name="to-run-a-date-compression" />Запуск сжатия данных

1. Выберите значок ![Поиск страницы или отчета](media/ui-search/search_small.png "Значок поиска страницы или отчета"), введите **Администрирование данных**, а затем выберите соответствующую ссылку.
2. Выполните одно из следующих действий:
    * Чтобы использовать мастер настройки для настройки сжатия по дате одного или нескольких типов данных, выберите **Мастер администрирования данных**.
    * Чтобы настроить сжатие для отдельного типа данных, выберите **Сжатие данных**, **Сжать операции**, а затем выберите данные для сжатия.

   > [!NOTE]
   > Вы можете сжимать только данные старше пяти лет. Если вы хотите сжать данные, которым меньше пяти лет, обратитесь к своему партнеру Майкрософт.

## <a name="see-also" />См. также

[Администрация](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
