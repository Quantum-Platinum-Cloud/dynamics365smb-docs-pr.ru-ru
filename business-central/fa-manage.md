---
title: Управление основными средствами (содержит видео)
description: Узнайте больше о функциях работы с основными средствами и получите обзор порядка работы с основными средствами и управления ими.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'machinery, buildings'
ms.search.form: '5604, 5606, 5664, 5601, 5602, 5658, 5603, 5671, 5641, 5629, 5633, 5634, 5649, 5622, 5650'
ms.date: 06/15/2021
ms.author: edupont
---
# <a name="managing-fixed-assets" />Управление основными средствами

Функциональные возможности по управлению основными средствами [!INCLUDE[prod_short](includes/prod_short.md)] позволяют получать информацию об основных средствах и обеспечивают правильную периодическую амортизацию. Кроме того, они позволяют отслеживать затраты на обслуживание, управлять страховыми полисами, учитывать транзакции основных средств и создавать различные отчеты и статистику.

Для каждого из основных средств необходимо настроить карточку, содержащую сведения об этом активе. Можно настроить здания или производственное оборудование как основное средство со списком компонентов, и их можно группировать разными способами, например по классам, подразделениям или расположению. После этого можно начинать приобретать, обслуживать и продавать основные средства. Можно также настроить бюджетные активы. Это позволит включать в отчеты ожидаемые приобретения и продажи.

Для отслеживания амортизации основных средств, а также других финансовых транзакций, связанных с основными средствами, требуется настроить одну или несколько книг амортизации для каждого основного средства в вашей организации. Амортизация выполняется путем запуска отчета для расчета периодической амортизации и заполнения журнала получающимися записями, готовыми к учету. [!INCLUDE[prod_short](includes/prod_short.md)] поддерживает несколько методов амортизации. Дополнительные сведения см. в разделе [Методы амортизации](fa-depreciation-methods.md). Можно настроить несколько книг амортизации для основного средства для различных целей, например, одну для налоговое отчетности, другую — для внутренней отчетности.

Для каждого основного средства можно записывать стоимость на обслуживание и следующую дату обслуживания. Отслеживание затрат на обслуживание может быть важным для бюджетирования и принятия решений о том, следует ли заменить основное средство.

Каждое основное средство может быть связано с одним или более страховых полисов. Таким образом можно легко проверить соответствие сумм страхового полиса и стоимости основных средств, которые связаны в полисе. Это также упрощает отслеживание ежегодных страховых взносов.

> [!NOTE]  
>   Можно записывать транзакции основного средства на странице **Журнал ГК учета основных средств** или на странице **Журнал ОС** в зависимости от назначения транзакций: для финансовой отчетности или для внутреннего управления. В справке для основных средств описывается только использование страницы **Журнал ГК учета основных средств**. Дополнительные сведения см. в разделе [Настройка амортизации основных средств](fa-how-setup-depreciation.md).

Прежде чем приступить к управлению основными средствами, необходимо настроить значения по умолчанию, учет ОС, учетные группы, ключи распределения, журналы и типы учета. Дополнительные сведения см. в разделе [Настройка основных средств](fa-setup.md).

В следующей таблице приводится последовательность задач со ссылками на разделы, в которых они описываются.

| Действие | Ссылка |
| --- | --- |
| Создать основные средства, назначить методы амортизации, учесть приобретения, ликвидационную стоимость и напечатать списки основных средств. |[Приобрести основные средства](fa-how-acquire.md) |
| Запись сервисных посещений, учет затрат на обслуживание и контроль затрат на обслуживание. |[Обслуживание основных средств](fa-how-maintain.md) |
| Обновить сведения о страховании, учесть стоимость приобретения в страховых полисах, изменить страховое покрытие, просмотреть статистику страхования и напечатать список страховых полисов. |[Страхование основных средств](fa-how-insure.md) |
| Реклассифицировать основные средства, переместить их в другие местоположения, разделить или объединить. |[Перемещение, разделение или объединение основных средств](fa-how-trans-split-combine.md) |
| Корректировать стоимость основных средств, учесть амортизацию и транзакции понижения стоимости |[Переоценка основных средств](fa-how-revalue.md) |
| Рассчитать амортизацию, учесть амортизацию и проанализировать амортизацию в отчетах по основным средствам. |[Амортизация основных средств](fa-how-depreciate-amortize.md) |
| Учесть транзакции выбытия, просмотреть операции книги выбытия и учесть частичные выбытия. |[Списание или выбытие основных средств](fa-how-dispose-retire.md) |
| Управлять бюджетами основных средств, бюджетировать стоимость приобретения, выбытие и амортизацию основных средств. |[Управление бюджетами основных средств](fa-how-manage-budgets.md) |

## <a name="video-overview" />Обзор видео

Следующее видео охватывает основы основных средств.

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4AegS?rel=0]

## <a name="see-related-microsoft-trainingtrainingpathsmanage-fixed-assets-transactions" />См. соответствующее [обучение Microsoft](/training/paths/manage-fixed-assets-transactions/)

## <a name="see-also" />См. также

[Настройка основных средств](fa-setup.md)  
[Изменение набора отображаемых функций](ui-experiences.md)  
[Финансы](finance.md)  
[Подготовьтесь к ведению бизнеса](ui-get-ready-business.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## <a name="includeprodshortincludesfreetrialmdmd" />[!INCLUDE[prod_short](includes/free_trial_md.md)]
 


[!INCLUDE[footer-include](includes/footer-banner.md)]
