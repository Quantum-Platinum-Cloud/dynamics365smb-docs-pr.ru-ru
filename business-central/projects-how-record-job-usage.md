---
title: Учет потребления или использования ресурсов работы и товаров
description: 'В этой статье описывается, как записать потребление или использование товаров или ресурсов для работ в управления проектами.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 03/08/2023
ms.custom: bap-template
---
# <a name="record-consumption-or-usage-for-jobs" />Учет потребления или использования для работ

Со страницы **Карточка работы** вы можете открыть страницу **Строки планирования работы**, чтобы просмотреть и записать использование различных частей вашей работы. Эта информация автоматически обновляется при изменении и перемещение информации между работами и журналами работ или счетами за работы. Для этого требуется включить **Применить связь использования по умолчанию** на странице **Настройка работ**. Подробнее см. в разделе [Настройка работ](projects-how-setup-jobs.md).  

Например, для строк планирования с типом **Бюджет** можно ввести количество ресурса и указать, какое количество должно быть перенесено в журнал работ. Если тип строки планирования имеет значение **К оплате**, можно ввести количество ресурса и указать, какое количество переместить в счет. Для получения дополнительной информации о выставлении счета клиенту см. [Выставление счетов за работы](projects-how-invoice-jobs.md). Сравнивая исходное количество, оставшееся количество или учтенное количество, вы можете быстро просмотреть информацию об использовании. Для получения информации об оценке бюджетных значений при планировании, см. в разделе [Управление бюджетами работ](projects-how-manage-budgets.md).  

В следующих процедурах описано, как регистрировать фактические (бюджетные) количества и расходы по журналу работ. В качестве альтернативы вы можете использовать документы о покупке для учета покупки для задания. Подробнее см. в разделе [Управление запасами для работы](projects-how-manage-project-supplies.md).

## <a name="to-record-usage-for-a-job-planning-line-of-type-budget" />Запись потребления для строки планирования работ типа "Бюджет"

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Работы**, а затем выберите связанную ссылку.  
2. Выберите соответствующую работу, затем выберите действие **Строки планирования работ**. 
3. Выберите строку планирования работ типа **Бюджет** или **Бюджет и к оплате**, для которых необходимо регистрировать потребление.   

    > [!NOTE]
    > Также можно учесть потребление для строки планирования работ типа **К оплате**. Как правило, строки используются для создания счетов, но также можно перемещение информации в журнал. Подробнее см. в разделе [Выставление счетов за работы](projects-how-invoice-jobs.md) 

4. В поле **Количество для переноса в журнал** введите число для перемещения. По умолчанию принимается количество, введенное в поле **Количество**.

    В поле **Остаток** отображается количество, оставшееся для завершения работы и перемещения в журнал.
5. Выберите действие **Создать строки журнала работ**.

    > [!TIP]
    > Если вы собираетесь добавить больше строк планирования работы для этой работы, подождите с этим шагом, пока вы не добавите все строки планирования работы.
6. На странице **Строка планирования работ по переносу работ** заполните поля по мере необходимости, затем нажмите кнопку **ОК**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Выберите действие **Открыть журнал работ**.  
8. На странице **Журнал работ** выберите соответствующую строку, затем выберите действие **Учет**.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

9. На странице **Строки планирования работы** просмотрите записанного потребление, проверив поля **Количество**, **Остаток** и **Количество для переноса в журнал**.  
10. Повторите шаги с 3 по 8, чтобы зарегистрировать дополнительное потребление.  

## <a name="to-create-job-journal-lines-manually" />Создание вручную строк журнала работ

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Журналы работы**, а затем выберите связанную ссылку.  
2. В поле **Код раздела** выберите соответствующий раздел журнала работ.  
3. В новой строке введите номер документа, номер работы, номер задания работы, тип и количество типа, который потребляется.  
4. Когда строки журнала работ выполнены, выберите действие **Учет**.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## <a name="to-view-job-usage-estimates-and-post-updates" />Просмотра оценок потребления работы и учет обновлений

Для просмотра потребления по работе вплоть до завершения проекта достаточно одного действия: воспользоваться пакетным заданием **Работа - расчет остаточного потребления** для всех задач до завершения работы включительно.  

Это позволяет отследить и сравнить первоначальные оценки с фактическими результатами, и при необходимости внести изменения или создать новые операции. Пусть, например, рассчитаны показали, что для выполнения работы необходимо 10 часов, а сегодняшний день выполнение заняло 15 часов. Программа позволяет добавить дополнительные 5 часов в существующей строке журнала или создать новую строку для записи этих дополнительных 5 часов как сверхурочных, что соответствует другому типу работы. Себестоимость и цена рассчитаны правильно и их можно учесть в журнале.  

> [!NOTE]  
> Операции товара приводят к созданию операций журнала товаров и уменьшению количества запасов. Пакетное задание **Учет себест. запасов в ГК** переносит себестоимость из книги запасов в Главную книгу. Операции ресурсов приводят к созданию операций книги ресурсов.  

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Журналы работы**, а затем выберите связанную ссылку.  
2. Выберите соответствующий журнал работ, затем выберите действие **Расчет остаточного потребления**.  
3. На странице **Работа - расчет остаточного потребления** введите номер документа и дату учета, которые следует вставить в журнал, затем выберите кнопку **ОК**.  
4. Обновите журнал, внеся в него все изменения, которые могут требоваться.  
5. Выберите **Учесть**.

## <a name="create-inventory-and-warehouse-pick-documents-for-a-job" />Создание документов инвентаризации и складского подбора для задания

Чтобы создавать документы инвентаризации и складского подбора для заданий, ваш администратор должен включить **Обновление функции: включение товарного и складского подбора из работ** на странице **Управление функциями**.

Функция добавляет действия **Создать товарный подбор** и **Создать складской подбор** в **карточку работы**. Чтобы создать или зарегистрировать документ подбора, используйте действия **Строки перемещения/подбора/размещения** или **Строки зарегистрированного подбора**. Подробнее см. в разделе [Потоки для производства, сборки и работ](design-details-internal-warehouse-flows.md).

Вы можете использовать действия при следующих условиях:

* **Статус** работы — **Открыто**.
* **Тип строки** строки планирования работы — **Бюджет** или **Бюджет и к оплате**.
* **Тип** строки планирования работы — **Товар**.
* **Требуется подбор** включено для связанного склада.
* **Расширенный подбор и размещение** отключено.

> [!NOTE] 
> Хотя настройка называется **Требуется подбор**, вы по-прежнему можете учитывать потребление непосредственно из строки журнала работ для склада. Если склад настроен так, что требуется обработка подбора, но не требуется обработка отгрузки, то для организации и печати информации по подбору следует использовать страницу **Подбор запасов**. Вы также используете страницу для ввода и учета результатов подбора, которые, в свою очередь, учитывают потребление товаров. 
> 
> Если склад настроен так, что требуется обработка как подбора, так и отгрузки, то есть выбраны поля **Требуется подбор** и **Требуется отгрузка** на странице **Карточка склада**, для обработки подбора используется страница **Складской подбор**. Складские подборы аналогичны подборам запасов. Разница в том, что вместо того, чтобы учитывать информацию о подборе, вы регистрируете подбор. Эта регистрация не учитывает потребление, она просто делает товары доступными для учета. Как менеджер склада, вы можете использовать журнал подбора для упорядочивания информации о подборе перед созданием отдельных складских инструкций по подбору.

## <a name="to-review-planning-lines-for-a-job-ledger-entry" />Проверка строк планирования для операции книги работ

После учета строк журнала работ можно увидеть строки планирования, связанные с записями журнала работ, которые были учтены.

> [!NOTE]  
> Для этого необходимо, чтобы для работы был установлен флажок **Применить связь использования**. Дополнительные сведения см. в разделе [Настройка работ](projects-how-setup-jobs.md).  

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Журналы работы**, а затем выберите связанную ссылку.  
2. Выберите соответствующий журнал работ, затем выберите действие **Книга операций**.  
3. На странице **Книга операций по работам** выберите действие **Показать связанные строки планирования работ**.

## <a name="see-related-microsoft-trainingtrainingpathspost-job-usage-sales" />См. соответствующее [обучение Microsoft](/training/paths/post-job-usage-sales/)

## <a name="see-also" />См. также

[Управление проектами](projects-manage-projects.md)  
[Финансы](finance.md)  
[Покупки](purchasing-manage-purchasing.md)  
[Продажи](sales-manage-sales.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
