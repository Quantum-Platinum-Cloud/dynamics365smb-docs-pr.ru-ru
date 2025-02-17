---
title: Настройка и публикация веб-служб КПЭ на основе бухгалтерских отчетов
description: 'В этой статье рассматривается, как отображать данные КПЭ по бухгалтерским отчетам на основе конкретных бухгалтерских отчетов.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 12/16/2022
ms.custom: bap-template
ms.search.form: '103, 104, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766'
---
# <a name="set-up-and-publish-kpi-web-services-based-on-financial-reports" />Настройка и публикация веб-служб КПЭ на основе бухгалтерских отчетов

На странице **Настройка веб-службы КПЭ бухгалтерского отчета** можно задать способ показа данных ключевых показателей эффективности (КПЭ), основанных на бухгалтерских отчетах, и указать, на каких конкретно бухгалтерских отчетах основываются эти КПЭ. При выборе действия **Опубликовать веб-службу** указанные данные КПЭ по бухгалтерским отчетам добавляются в список опубликованных веб-служб на странице **Веб-службы**.

> [!NOTE]
> Когда вы используете эту веб-службу, даты закрытия не включаются в ваш набор данных. Можно использовать фильтры в Power BI для анализа различных периодов времени.

## <a name="set-up-and-publish-a-kpi-web-service-based-on-financial-reports" />Настройка и публикация веб-службы КПЭ на основе бухгалтерских отчетов
  
1. Выберите значок ![Лампочка, которая открывает функцию «Что вы хотите сделать»](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Настройка веб-службы КПЭ бухгалтерского отчета**, а затем выберите соответствующую ссылку.
2. Заполните поля на экспресс-вкладке **Общие сведения**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. На экспресс-вкладке **Определения строк** заполните поля.
4. Повторите шаг 3 для всех бухгалтерских отчетов, на которых должна быть основана служба КПЭ по бухгалтерским отчетам.  
5. Для просмотра или редактирования выбранного бухгалтерского отчета на экспресс-вкладке **Определения строк** выберите действие **Изменить определение строк**.
6. Для просмотра настроенных данных КПЭ по бухгалтерским отчетам выберите действие **Веб-служба КПЭ бухгалтерского отчета**.
7. Для публикации веб-службы КПЭ по бухгалтерским отчетам выберите действие **Опубликовать веб-службу**.

Теперь вы можете создавать финансовые отчеты в Power BI на основе веб-службы или служб, которые вы создали.

> [!NOTE]  
> Опубликовать веб-службу КПЭ также можно, наведя указатель на объект страницы **Настройка веб-службы КПЭ бухгалтерского отчета** на странице **Веб-службы**. Подробнее см. в статье [Публикация веб-службы](across-how-publish-web-service.md).

## <a name="see-also" />См. также

[Финансовая бизнес-аналитика](bi.md)  
[Финансы](finance.md)  
[Настройка финансов](finance-setup-finance.md)  
[Главная книга и план счетов](finance-general-ledger.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
