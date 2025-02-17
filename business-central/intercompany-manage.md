---
title: Управление межфирменными транзакциями
description: С помощью функции межфирменного учета можно упростить бизнес-процессы и транзакции между компаниями в пределах одной организации.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bhielse
ms.topic: conceptual
ms.date: 02/06/2023
ms.custom: bap-template
ms.search.keywords: 'IC, group, consolidation, affiliate, subsidiary'
ms.search.form: '605,'
---
# <a name="managing-intercompany-transactions" />Управление межфирменными транзакциями

Межфирменные транзакции могут быть удобны для предприятий, которые имеют более одного юридического лица и ведут по ним раздельный учет. Например, это выгодно для компаний, у которых есть дочерние компании на нескольких международных рынках или в разных регионах. Либо организация может включать в себя несколько компаний, но не иметь соответствующего количества бухгалтерских и административных отделов. Межфирменные транзакции упрощают и оптимизируют бизнес-процессы и транзакции между организациями, состоящими в межфирменном партнерстве.

Если вы указали отношения клиента и поставщика для межфирменных транзакций, партнеры вводят информацию в документы продажи и покупки только один раз. Соответствующий документ автоматически создается у другого партнера, участвующего в транзакции. Сопоставление плана счетов и измерений помогает обеспечить отображение данных в нужных местах.  

Можно назвать четыре главных преимущества функций межфирменного учета:  

* Увеличение производительности в результате экономии времени и упрощения транзакций  
* Минимизация ошибок благодаря однократному вводу информации и автоматическим обновлениям в масштабе всей системы  
* Полный журнал аудита, полное видение бизнес-процессов и истории транзакций  
* Эффективные, экономичные транзакции с филиалами и дочерними организациями  

## <a name="streamline-the-flow-of-business-activities" />Оптимизация выполнения бизнес-операций

Межфирменные транзакции позволяют распределять документы продаж и покупок, а также операции финансового журнала по всем офисам, отделам продаж и дочерним организациям. Распределение транзакций экономит время и повышает эффективность всей организации за счет уменьшения объема вводимых данных. Оно устраняет необходимость в отправке, получении, выводе на печать и архивировании документов продаж и покупок.  

Вы полностью контролируете все документы по транзакциям. Например, вы можете отклонить отправленный вам документ **Сторнирование учета в журнале** и **Отмена приходных/расходных накладных** для внесения корректировок. Или, в случае покупки у партнера или дочерней компании, можно обновлять заказ на покупку до тех пор, пока продавец не отгрузит товары.  

Когда вы вводите транзакцию, вам не нужно указывать используемые счета. Вы просто выбираете межфирменного партнера. Функция межфирменных транзакций создает строки финансового журнала, которые обеспечивают баланс книг обеих организаций, участвующих в транзакции. В счетах дебиторов и кредиторов пользователь назначает межфирменный код партнера любому клиенту или поставщику. С этого момента для всех заказов и счетов-фактур по транзакциям между этими организациями создаются соответствующие документы в компании-партнере. В результате обеспечивается правильный баланс счетов.  

Функция межфирменного учета ориентирована на документы продажи и покупки, а также строки финансового журнала, обеспечивая возможность совершать транзакции между несколькими базами данных [!INCLUDE [prod_short](includes/prod_short.md)]. Например:

* разные страны/регионы;
* несколько валют;
* разные планы счетов;
* разные измерения;
* разные номенклатурные номера.  

Для межфирменных транзакций используется несколько типов операций и документов:  

* Операции финансового журнала
* Заказы на покупку и продажу
* Счета на покупку и продажу
* Кредит-ноты
* Возвраты заказов

Когда вы настраиваете межфирменные транзакции, вы создаете список межфирменных партнеров, межфирменный план счетов и межфирменные измерения. После этого вы можете создавать транзакции в финансовых журналах межфирменного учета.

> [!NOTE]
> Финансовый журнал сам по себе не включает валюты. Он конвертирует все суммы в местную валюту по текущему обменному курсу.

После того как вы создадите бизнес-партнеров в качестве клиентов и поставщиков и назначите им коды межфирменных партнеров, они смогут обмениваться межфирменными документами покупки и продажи, включая товары и товарные издержки. 

> [!NOTE]
> Организации могут использовать межфирменный обмен не для всех типов данных. Счета-фактуры не отправляются деловым партнерам через внутрифирменные процессы. В то же время, счета-фактуры продаж, отправляемые посредством межфирменных процессов, будут создаваться как счета-фактуры покупки в компании-получателе.

Для межфирменных процессов может быть актуальна консолидация финансовых данных. Дополнительные сведения см. в разделе [Консолидация финансовых данных из нескольких организаций](finance-consolidated-company-reporting.md).

В следующей таблице приводится последовательность задач со ссылками на статьи, в которых они описываются.

|Задача |Ссылка|
|---|---|
|Создание межфирменных поставщиков и клиентов в качестве партнеров и настройка межфирменного плана счетов.|[Настройка межфирменных взаимодействий](intercompany-how-setup.md)|
|Использование межфирменных документов или журналов для учета транзакций, выполненных с межфирменными партнерами.|[Работа с межфирменными документами и журналами](intercompany-how-work-documents-journals.md)|
|Упорядочение и обработка входящих и исходящих транзакций, которыми вы обмениваетесь с межфирменными партнерами.|[Управление межфирменными входящими и исходящими ящиками](intercompany-how-manage-intercompany-inbox.md)|
|Используйте межфирменные проводки для распределения затрат между компаниями-партнерами.|[Распределение затрат между внутрифирменными партнерами](intercompany-allocate-costs.md)|

## <a name="see-also" />См. также

[Финансы](finance.md)  
[Настройка финансов](finance-setup-finance.md)  
[Работа с финансовыми журналами](ui-work-general-journals.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## <a name="includeprodshortincludesfreetrialmdmd" />[!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]
