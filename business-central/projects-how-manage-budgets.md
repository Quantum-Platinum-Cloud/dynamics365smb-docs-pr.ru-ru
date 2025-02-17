---
title: Настройка и управление бюджетом для работы
description: Далее описывается процедура планирования ресурсов и прогнозирования и контроля себестоимости для проекта путем настройки бюджета для каждой работы.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'project budget, forecast'
ms.search.form: '1002, 1007'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="manage-job-budgets" />Управление бюджетами работ

Бюджет можно настроить для каждой работы. Бюджет необходим для планирования ресурсов, выделенных для выполнения работы. Бюджет может быть общим, с небольшим количеством операций, или же он может содержать больше операций, которые разделены по уровням деятельности. Затем можно сравнивать бюджетные суммы с фактическим потреблением, занесенным в журнал работ. Контролируя различия между фактическим и бюджетным потреблением, можно контролировать текущий проект и улучшить качество будущих работ за счет снижения риска неправильной оценки затрат.

Следующая процедура показывает, как оценить бюджетные затраты во время планирования. Информацию о регистрации бюджетных и фактических цен и затрат для работ см. в разделе [Регистрация потребления для работ](projects-how-record-job-usage.md).  

## <a name="a-namejobbudgetcostsa-to-estimate-the-budgeted-costs-for-a-job" /><a name="JobBudgetCosts"></a> Оценка бюджетных затрат для работы
Когда клиент хочет знать цену работы, накладная по которой будет выставлена на основе потребления, необходимо определить бюджетные затраты на работу. Для этого используйте страницу **Строки задач по работе**.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Работы**, а затем выберите связанную ссылку.  
2. Откройте соответствующую работу.
3. Выделите строку задачи типа "Учет", затем выберите действие **Строки планирования работ**.
4. На новой строке заполните поля, как требуется. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]   

Для поля **Тип строки** см. следующую информацию.  

| Тип строки | Описание |
| --- | --- |
| **Бюджет и к оплате** |Суммы затрат и цен, введенные в строку планирования, представляют собой бюджетные затраты для данной строки планирования. По этой цене будет выставлен счет. |
| **Бюджет** |Клиенту не оплачивает потребление. Потребление не может быть переведено в счет, но будет использоваться в расчете НЗП. |
| **К оплате** |Клиенту оплачивает потребление. Потребление переводится в счет на основании количества, указанного в поле Переносимое в счет количество. |

> [!NOTE]  
> Поле **Плановая дата доставки** для строки планирования содержит дата, когда ожидается завершение потребления, связанного со строкой планирования. Это также дата, когда строка планирования может быть перенесена в счет по продаже и учтена. <br /><br /> В базовой задаче работы на странице **Карточка работы** поля **Дата начала** и **Дата окончания** содержат, соответственно, значение поля **Плановая дата доставки** на самой ранней и самой поздней строках планирования работы на связанной странице **Строки планирования работ**.

> [!NOTE]  
>   При заполнении поля **Количество** вся информация об общих ценах и затратах будет рассчитана и заполнена для данной строки планирования. Ее можно изменить в любое время.

На странице **Карточка работы** можно увидеть общие бюджетные затраты, бюджетную цену, себестоимость к оплате и сумму к оплате для каждой задачи.

Информацию о регистрации бюджетных и фактических цен и затрат для работ см. в разделе [Регистрация потребления для работ](projects-how-record-job-usage.md).

## <a name="see-related-microsoft-trainingtrainingmodulesset-up-job-planning-lines" />См. соответствующее [обучение Microsoft](/training/modules/set-up-job-planning-lines/)

## <a name="see-also" />См. также

[Управление проектами](projects-manage-projects.md)  
[Финансы](finance.md)  
[Покупки](purchasing-manage-purchasing.md)  
[Продажи](sales-manage-sales.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
