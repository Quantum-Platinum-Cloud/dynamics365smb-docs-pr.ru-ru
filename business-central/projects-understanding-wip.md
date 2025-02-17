---
title: Методы расчета НЗП для расчета и записи хода выполнения работ
description: 'Описываются различные методы НЗП, которые можно использовать для учета, отслеживания и расчета финансовой информации для текущих незавершенных работ.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'work in process, work in progress, calculate project WIP'
ms.search.form: 1010
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="understanding-wip-methods-in-project-management" />Понимание методов НЗП в управлении проектами

По мере выполнения работы, материалы, ресурсы и т. д. потребляются и подлежат учету. Незавершенное производство (НЗП) — это функция, позволяющая в процессе выполнения работы оценивать ее стоимость с финансовый точки зрения в Главной книге, пока работы еще не завершены. В большинстве случаев затраты можно учесть до выставления счета по работе. Если учитывать только расходы, финансовый отчет будет неточным.

Для трассировки стоимости в Главной книге, можно рассчитать НЗП и учесть стоимость в Главной книге. Для получения дополнительной информации см. раздел [Отслеживание хода выполнения работ и производительности](projects-how-monitor-progress-performance.md).

[!INCLUDE[prod_short](includes/prod_short.md)] поддерживает следующие методы расчета и регистрации стоимости незавершенного производства.

| Метод НЗП | Формула расчета | Описание расчета |
| --- | --- | --- |
| Себестоимость |Признанный доход = К оплате (цена по счету)<br /><br /> Оценочная итоговая себестоимость = Итоговая цена к оплате x Коэффициент бюджетной себестоимости<br /><br /> Затраты НЗП = (процент завершения -выст. счет (%)) x оценочная итоговая себестоимость<br /><br /> Процент завершения = Потребл. (итоговая себест.)/Бюджет (итог. себест.)<br /><br />Выст. счет (%) = К оплате (цена по счету)<br /><br /> Признанные затраты общей цены к оплате = Потребл. (итоговая себест.) – НЗП |Расчет себестоимости начинается с вычисления стоимости предоставленного путем вычисления доли оценочной итоговой себестоимости на основе процента завершения. Зачтенные затраты вычитаются путем вычисления доли оценочной итоговой себестоимости на основе процентного отношения суммы выставленного счета.<br /><br />Для этого вычисления требуется правильно ввести значения "К оплате (общая цена)", "Бюджет (итог. цена)" и "Бюджет (итог. себест.)" для всей работы. |
| Себестоимость продаж |Признанный доход = К оплате (цена по счету)<br /><br /> Признанные затраты = Бюджет (итог. себест.) x Выст. счет (%)<br /><br /> Выст. счет (%) = К оплате (цена по выст. счетам)/К оплате (общая цена)<br /> ("Выст. счет (%)" представляет собой столбец в строках рабочего задания)<br /><br /> Затраты НЗП = Потребл. (итоговая себест.) - Признанные затраты |Расчет себестоимости продаж начинается с вычисления признанных затрат. Затраты признаются пропорционально бюджетной итоговой себестоимости.<br /><br /> Для этого вычисления требуется правильно ввести значения "К оплате (общая цена)" и "Бюджет (итог. себест.)" для всей работы. |
| Стоимость продаж |Признанные затраты = Потребл. (итоговая себест.)<br /><br /> Признанный доход = Потребл. (общая цена) x Ожидаемая доля по счетам<br /><br /> Возмещение издержек (%) = К оплате (общая цена)/Бюджет (итог. цена)<br /><br /> Продажи НЗП = Признанные продажи - К оплате (цена по выст. счетам) |При расчете по методу "Сумма реализации" доход признается пропорционально в соответствии с отношением величины "Потребл. (итоговая себест.)" к ожидаемому возмещению издержек.<br /><br /> Для этого вычисления требуется правильно ввести значения "К оплате (общая цена)" и "Бюджет (итоговая цена)" для всей работы. |
| Процент завершения |Признанные затраты = Потребл. (итоговая себест.)<br /><br /> Признанный доход = К оплате (общая цена) x Процент завершения<br /><br /> Процент завершения = Потребл. (итоговая себест.)/Бюджет (итог. себест.)<br /> (Зафиксировано в поле **Выполненные затраты (%)** в строках рабочих заданий)<br /><br /> Продажи НЗП = Признанные продажи - К оплате (цена по выст. счетам) |При расчете по методу "Процент завершения" доход признается пропорционально на основании процента завершения, т. е. отношения итоговой себестоимости потребления к значению бюджетной себестоимости.<br /><br /> Для этого вычисления требуется правильно ввести значения "К оплате (общая цена)" и "Бюджет (итог. себест.)" для всей работы. |
| Выполненный контракт |Сумма НЗП = Сумма себестоимости НЗП = Потребл. (итоговая себест.)<br /><br /> Сумма продаж по НЗП = К оплате (цена по выст. счетам) |При использовании метода "Выполненный контракт" доходы и затраты не признаются до завершения работы. Данный метод следует применять, если оценки затрат и доходов по данной работе слишком неопределенные.<br /><br /> До завершения работы все потребление учитывается на счете затрат НЗП (активы), а все продажи по выставленным счетам учитываются на счете продаж НЗП, по которым выставлены счета (пассивы). |

## <a name="see-related-microsoft-trainingtrainingpathscalculate-post-job-wip" />См. соответствующее [обучение Microsoft](/training/paths/calculate-post-job-wip/)

## <a name="see-also" />См. также

[Управление проектами](projects-manage-projects.md)  
[Финансы](finance.md)  
[Покупки](purchasing-manage-purchasing.md)  
[Продажи](sales-manage-sales.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
