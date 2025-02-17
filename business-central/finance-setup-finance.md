---
title: Настройка финансовых процессов
description: Узнайте о необходимых задачах по настройке финансов для своего бизнеса в соответствии требованиями учет и аудита.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'accounting, auditing, bookkeeping'
ms.date: 08/19/2022
ms.author: edupont
---
# <a name="setting-up-finance" />Настройка финансов

Прежде чем вы сможете начать свой бизнес, вы должны указать, как вы хотите управлять финансовыми процессами компании. Сначала вы настраиваете основу учетных записей организации: план счетов (COA). Затем настраиваются учетные группы, что позволяет сделать более эффективным процесс назначения используемых по умолчанию учетных счетов главной книги клиентам, поставщикам и товарам.

Некоторые финансовые настройки могут выполняться автоматически с помощью мастеров настройки, а некоторые — вручную. Узнайте больше в разделе [Подготовьтесь к ведению бизнеса](ui-get-ready-business.md). На странице **Настройка ГК** вы указываете, как обрабатывать разные процессы учета в вашей организации. Например, эту страницу следует использовать для определения подробностей округления счета, для определения кода валюты по локальной валюте (руб.), форматов адресов, а также для выяснения потребности использования дополнительной отчетной валюты. Подробнее см. в разделе [Принципы работы с главной книгой и планом счетов](finance-general-ledger.md).  

Можно использовать измерения для добавления различных типов информации к каждой транзакции. Можно настроить основные измерения организации, такие как *Проекты* и *Подразделения*. Позже добавьте дополнительные измерения, когда они вам понадобятся. Например, вы можете настроить временные измерения для использования в течение ограниченного периода времени, например, во время кампании продаж. Подробнее в разделе [Работа с измерениями](finance-dimensions.md).

Многие задачи настройки должны быть выполнены до начала записи финансовых транзакций, при этом большую часть настроек можно настраивать по мере необходимости. Тем не менее, есть также и необязательные задачи настройки. Например, межфирменный учет и консолидации требуется настраивать лишь в случае работы с несколькими организациями. И другие задачи настройки, такие как задание периода, в течение которого разрешен учет, должны периодически повторяться.  

В следующей таблице приводится последовательность задач со ссылками на разделы, в которых они описываются.

| По | Ссылка |
| --- | --- |
|Просмотр или редактирование счетов главной книги, для которых учитываются все записи главной книги|[Настройка или изменение плана счетов](finance-setup-chart-accounts.md)|
| Укажите, как вы хотите получать оплату от клиентов и как вы хотите платить своим поставщикам. |[Настройка способов оплаты](finance-payment-methods.md) |
| Укажите условия оплаты для управления сроками оплаты и вычисления возможных скидок оплаты.|[Настройка условия платежа](finance-payment-terms.md) |
| Определяйте учетные группы, которые сопоставляют объекты, такие как клиенты, поставщики, товары, ресурсы и документов продажи и покупки со счетами главной книги. |[Настройка учетных групп](finance-posting-groups.md)|
|Создайте финансовые отчеты и задайте категории счетов, которые определяют содержимое финансовых диаграмм и отчетов, например балансового отчета и отчета о прибылях и убытках.|[Подготовка Financial Reporting с помощью финансовых данных и категорий счетов](bi-how-work-account-schedule.md)|
|Настройте отклонение, при котором система закрывает счет, даже если платеж, включая все скидки, не полностью покрывает сумму счета.|[Работа с отклонениями в оплате и отклонениями скидки по оплате](finance-payment-tolerance-and-payment-discount-tolerance.md)|
| Настройте финансовые периоды. |[Работа с учетными периодами и финансовыми годами](finance-accounting-periods-and-fiscal-years.md) |
|Настройте условия выставления счета, которые будут напоминать вашим клиентам о необходимости оплаты.|[Настройка условий и уровней напоминаний](finance-setup-reminders.md)|
| Определите способ подачи в налоговые органы отчетов о суммах налога на добавленную стоимость (НДС), собранного в результате продаж. |[Настройка налога на добавленную стоимость (НДС)](finance-setup-vat.md)|
|Подготовьтесь к обработке нереализованного НДС в связи с методами бухгалтерского учета на основе наличных средств.|[Настройка нереализованного НДС для учета на основании кассы](finance-setup-unrealized-vat.md)|
|Определите иностранные валюты, в которых вы торгуете или в которых сообщаете об операциях.|[Настройка валют](finance-set-up-currencies.md)|
| Настройка функций продаж и покупок для обработки платежей в иностранных валютах.|[Включение операций книги в разных валютах](finance-how-enable-application-ledger-entries-different-currencies.md)
|Определите одну или несколько дополнительных валют, чтобы суммы автоматически сообщались как в локальной валюте (LCY), так и в дополнительной отчетной валюте по каждой операции в главной книге (ГК) и в других операциях.|[Настройка дополнительной отчетной валюты](finance-how-setup-additional-currencies.md)|
|Периодически регулируйте эквиваленты дополнительных валят для учета колебаний курсов валют.|[Обновление валютных курсов](finance-how-update-currencies.md)|
|Определите несколько процентных ставок для использования для различных периодов для задержанных платежей в торговых транзакциях.|[Настройка нескольких процентных ставок](finance-how-to-set-up-multiple-interest-rates.md)|
|Организуйте автоматическое округление сумм при создании счетов.|[Настройка округления счета](finance-set-up-invoice-rounding.md)|
| Добавление новых счетов для существующего плана счетов. |[Настройка плана счетов](finance-setup-chart-accounts.md) |
| Настройка диаграмм бизнес-аналитики для анализа движения денежных средств. |[Настройка анализа движения денежных средств](finance-setup-cash-flow-analyses.md) |
|Включение выставления счетов клиенту, который не настроен в системе.|[Настройка клиентов, оплачивающих наличными](finance-how-to-set-up-cash-customers.md)|
| Настройка отчетности Интрастат и отправка отчета в уполномоченные органы. | [Настройка и подача отчетности Интрастат](finance-how-setup-report-intrastat.md)|
|Убедитесь, что при учете в журнале операция в журнале распределена между различными счетами, такими как количество, процент или сумма.|[Использование ключей распределения в финансовых журналах](ui-how-use-allocation-keys-general-journals.md)|
|Настройка кодов источников и коды причин, чтобы помочь при отслеживании журналов аудита.|[Настройка кодов источников и кодов причин для журналов аудита](finance-setup-trail-codes.md)|
|Укажите отчеты по умолчанию, которые будут использоваться для различных типов документов.|[Выбор отчета в Business Central](across-report-selections.md)|

> [!TIP]
> В зависимости от вашего географического положения некоторые страницы Business Central могут содержать поля, которые не описаны в перечисленных выше статьях, поскольку они применяются к локальным функциям или настройкам. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## <a name="see-related-microsoft-trainingtrainingpathsset-up-financial-management-dynamics-365-business-central" />См. соответствующее [обучение Microsoft](/training/paths/set-up-financial-management-dynamics-365-business-central/)

## <a name="see-also" />См. также

[Финансы](finance.md)  
[Выверка банковских счетов](bank-manage-bank-accounts.md)  
[Работа с измерениями](finance-dimensions.md)  
[Импорт бизнес-данных из других финансовых систем](across-import-data-configuration-packages.md)  
[Анализ движения денежных средств в организации](finance-analyze-cash-flow.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## <a name="includeprodshortincludesfreetrialmdmd" />[!INCLUDE[prod_short](includes/free_trial_md.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
