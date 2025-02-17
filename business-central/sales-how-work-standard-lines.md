---
title: Стандартные строки типовых продаж
description: 'Настройте часто используемые строки продаж, а затем вставляйте их в документы продажи, чтобы быстро заполнять строки стандартной информацией.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'trade, sell, replenishment'
ms.search.form: 172
ms.date: 07/06/2022
ms.author: edupont
---
# <a name="create-recurring-sales" />Создание типовых продаж

Если вам часто приходится создавать строки продажи с одинаковыми данными, вы можете настроить стандартные строки, которые затем можно вставлять в документы типовых продаж, например для типовых заказов на пополнение.  

## <a name="set-up-recurring-sales-lines" />Настройка строк типовых продаж

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Строки типовых продаж**, а затем выберите связанную ссылку.  
2. На странице **Строки типовых продаж** выберите действие **Создать**.  
3. На экспресс-вкладке **Общее** заполните необходимые поля. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. На экспресс-вкладке **Строки** заполните поля для подготовки строк продажи, которые отражают стандартные строки, которые ожидаются как типовые в документах продажи.  

> [!NOTE]
> Невозможно определить цены в строках типовых продажи, поскольку цены, скидки и т. д, вычисляются на базе фактических документов продажи после вставки строк типовых продажи.

[!INCLUDE [line-no-info](includes/line-no-info.md)]

## <a name="assign-recurring-sales-lines-to-a-customer" />Присвоение клиенту строк типовых продаж

Назначьте одну или несколько строк типовых продаж клиенту, чтобы они были доступны для вставки в документы продажи для этого клиента.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Клиенты**, а затем выберите связанную ссылку.
2. Откройте карточку для соответствующего клиента.
3. Выберите значение **Строки типовых продаж**.
4. На странице **Строки типовых продаж** выберите коды для строк типовых продаж, которые должны быть доступны для вставки в документы продажи для этого клиента.
5. Заполните дополнительные поля, чтобы определить, когда, как и где строки типовых продаж будут использоваться.  

    Если вы планируете использовать типовые строки продажи, заданные вместе с пакетным заданием **Создание типовых счетов продажи**, используйте поля **Действует с даты** и **Действует до даты**, чтобы ограничить время создания типовых строк продажи для создания счетов. Дополнительные сведения см. в разделе [Создание нескольких счетов продаж на основе стандартных строк продаж](sales-how-work-standard-lines.md#create-multiple-sales-invoices-based-on-recurring-sales-lines)

    Также можно также определять метод оплаты прямого дебета и мандат прямого дебета. Счета продажи, созданные с помощью пакетного задания **Создание типовых счетов продажи**, будут включать информацию, необходимую для получения платежей с прямым дебетом SEPA. Дополнительные сведения см. в разделе [Сбор платежей с прямым дебетованием SEPA](finance-collect-payments-with-sepa-direct-debit.md).

6. В четырех полях, в которых выбирается, как строки вставляются в четыре типа документов, выберите один из следующих параметров:

|Параметр|Описание|
|------|-----------|
|**Ручной**|Следует вручную найти и вставить стандартную строку продаж, существующую для клиента.|
|**Автоматически**|Если несколько строки стандартных продаж существуют для клиента, вы получите уведомление, в котором можно выбрать, какую из них вставить. Если имеется только одна строка стандартных продаж, она вставляется автоматически.<br /><br />Это работает только в случае, когда новый документ был создан из списка документов, например путем выбора действия **Создать** на странице **Заказы на продажу**. Это не работает, если документ был создан, например, из карточки клиента.|
|**Всегда спрашивать**|Появляется уведомление, и отображаются все существующие строки стандартных продаж, чтобы можно было выбрать одну.

## <a name="insert-recurring-sales-lines-on-a-sales-invoice" />Вставка строк типовых продаж в счет продажи

Если существуют строки типовых продаж для клиента, вы можете вставить сами (или их может вставить кто-то другой) в документы продажи всех типов, например в счета продажи. Если активирован параметр **Всегда спрашивать**, то при назначении строк типовых продаж клиентам вы получите уведомление о том, существуют ли строки типовых продаж.

1. Выберите значок ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать"), значок введите **Счета продажи**, а затем выберите связанную ссылку.
2. Откройте счет продажи, в который требуется вставить одну или несколько стандартных строк.
3. Выберите значение **Получить строки типовых продаж**.
4. На странице **Строки типовых продаж** нажмите кнопку выбора в поле **Код**, а затем выберите набор стандартных строк продажи.
5. Нажмите кнопку **ОК**, чтобы вставить в счет стандартные строки продажи, которые можно потом использовать их повторно или изменить.

## <a name="create-multiple-sales-invoices-based-on-recurring-sales-lines" />Создание нескольких счетов продажи на основе строк типовых продаж

Можно использовать пакетное задание **Создание типовых счетов продажи** для создания счетов продаж в соответствии со стандартными строками продаж, которые назначены клиентам, и с учетными датами в пределах дат "Действительно с" и "Действительно по", указанных в стандартных строках продажи.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Создание типовых счетов продажи**, а затем выберите связанную ссылку.
2. На странице **Создание типовых счетов продажи** заполните поля по мере необходимости.
3. В поле фильтра **Код** введите код для стандартных строк продажи, назначенных клиенту, для которого требуется создать счета продаж.
4. Нажмите кнопку **ОК**.

Для клиентов создаются счета продажи с указанным стандартным клиентским кодом продажи, а также всеми заданными сведениями о прямом дебете для учета на определенную дату.

## <a name="see-related-microsoft-trainingtrainingmodulescreate-sales-documents-dynamics-365-business-central" />См. соответствующее [обучение Microsoft](/training/modules/create-sales-documents-dynamics-365-business-central/)

## <a name="see-also" />См. также

[Продажи](sales-manage-sales.md)  
[Настройка продаж](sales-setup-sales.md)  
[Создание типовых строк покупок](purchasing-how-work-recurring-purchase-lines.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
