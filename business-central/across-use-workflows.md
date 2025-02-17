---
title: Использование рабочих процессов утверждения
description: 'Вы можете настроить и использовать рабочие процессы для связи задач бизнес-процесса, таких как автоматический учет или запрос и предоставление утверждения для новых записей.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: '1500, 1501, 1503, 1504, 1505'
ms.date: 09/13/2022
ms.author: edupont
---
# <a name="use-approval-workflows" />Использование рабочего процесса утверждения

Рабочий процесс — это последовательность задач, которые запускаются действием, условием или правилом. Рабочие процессы обычно реализуются для интеграции бизнес-логики в организации, например, для разделения обязанностей, унификации процессов или применения рекомендаций.

Рабочие процессы могут быть предназначены для создания запросов на утверждение изменения полей записей с сохранением старых данных на случай, если запрос не будет утвержден. Новое значение не будет реализовано до тех пор, пока не будет одобрен последний запрос.

Бизнес-логика может быть утверждением:

- Новые основные данные, такие как счета главной книги (ГК), клиенты, поставщики или номенклатуры.
- Изменения в полях в существующих записях, содержащих важную информацию, например **Номер банковского счета продавца** или **Лимит кредита клиента**.
- Изменения в полях в существующих записях, содержащих важную бизнес-информацию, например **Цены продажи товаров**.
- Новые пользователи или изменения в разрешениях пользователей.
- Документы покупки.
- Документы продажи.
- Входящие документы.
- Финансовые журналы перед разноской.

На следующем рисунке показан пример рабочего процесса с последовательным утверждением, инициированным пользователем. При запуске рабочего процесса для первого утверждающего создается запрос на утверждение.  

![Иллюстрация рабочего процесса с последовательным утверждением.](media/Workflows/approval-flow.png)

Вы видите на приведенном выше рисунке, как запрос должен быть одобрен первым утверждающим, прежде чем он будет отправлен следующему утверждающему. Если запрос не одобрен первым утверждающим, он никогда не перейдет к следующему утверждающему.

Маршрут, взятый из первоначального запуска рабочего процесса, может варьироваться в зависимости от характера утверждения.  

На следующем рисунке показано параллельное утверждение, инициированное пользователем. Параллельное утверждение означает, что запрос на утверждение отправляется всем утверждающим одновременно.  

![Иллюстрация рабочего процесса с параллельным утверждением.](media/Workflows/approval-flow-2.png)

Однако рабочий процесс не завершается до тех пор, пока все запросы не будут утверждены, как показано на следующем рисунке:  

![Иллюстрация отклоненного рабочего процесса с параллельным утверждением.](media/Workflows/approval-flow-3.png)

> [!NOTE]  
> Для рабочего процесса с несколькими утверждающими все утверждающие должны утвердить каждый шаг, прежде чем рабочий процесс сможет перейти к следующему событию. Утверждение всего одним утверждающим лицом не приведет к дальнейшему развитию рабочего процесса.

Можно настроить и использовать рабочие процессы, связывающие задачи бизнес-процесса, выполняемые различными пользователями. Также возможно создать один и тот же рабочий процесс более одного раза. Каждый рабочий процесс может запускаться событием с использованием разных фильтров. Это полезно, если запрос на утверждение для одного отдела должен быть утвержден одним утверждающим, тогда как запросы на утверждение для других отделов должны быть утверждены другим утверждающим. Системные задачи, такие как автоматический учет, могут включаться в качестве шагов рабочего процесса, предшествующих задачам пользователя или выполняемых после них. Типичные шаги рабочего процесса — запрос и выдача разрешения на создание новых записей.  

Прежде чем начать использование рабочих процессов, необходимо произвести настройку пользователей рабочих процессов, создать рабочие процессы (возможно, перед этим потребуется настройка кода) и определить, как пользователи будут получать уведомления. Узнайте больше в разделе [Настройка рабочих процессов](across-set-up-workflows.md).

> [!NOTE]  
> Типичные шаги рабочего процесса включают пользователей, запрашивающих утверждение задач, и утверждающих, принимающих или отклоняющих запросы на утверждение. Поэтому многие разделы Справки, посвященные рабочим процессам, касаются утверждений.  

 В следующей таблице приводится последовательность задач со ссылками на статьи, в которых они описываются.  

| **Задача** | **Раздел** |
|--|--|
| Настройте запуск рабочего процесса утверждения на тот момент, когда произойдет первое событие входа. | [Включение рабочих процессов утверждения](across-how-to-enable-workflows.md) |
| Запрос утверждения для задачи, принятие, отклонение или делегирование утверждений утверждающим; и отправка или просмотр уведомлений об утверждении. | [Как использовать рабочие процессы утверждения](across-how-use-approval-workflows.md) |
| Создание шагов рабочего процесса, которые ограничивают использование записей определенного типа до наступления определенного события, например утверждения записи. | [Ограничение и разрешение использования записи](across-how-to-restrict-and-allow-usage-of-a-record.md) |
| Просмотр экземпляров шагов рабочего процесса со статусом **Завершено**. | [Просмотр архивированных экземпляров шагов рабочих процессов](across-how-to-view-archived-workflow-step-instances.md) |
| Удаление рабочего процесса утверждения, про который известно, что он больше не будет использоваться. | [Удаление рабочих процессов утверждения](across-how-to-delete-workflows.md) |

## <a name="see-related-microsoft-trainingtrainingmodulescreate-workflows" />См. соответствующее [обучение Microsoft](/training/modules/create-workflows/)

## <a name="see-also" />См. также

[Настройка рабочих процессов утверждения](across-set-up-workflows.md)  
[Рабочий процесс](across-workflow.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
