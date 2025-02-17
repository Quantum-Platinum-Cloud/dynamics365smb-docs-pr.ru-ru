---
title: Как удалять рабочие процессы утверждения
description: 'Если вы уверены, что рабочий процесс уже не используется, то его можно удалить. Все экземпляры шагов рабочего процесса, определенные в рабочем процессе, должны иметь статус **Завершено**.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: '1500,'
ms.date: 09/08/2022
ms.author: edupont
---
# <a name="delete-approval-workflows" />Удаление рабочих процессов утверждения

Если вы уверены, что рабочий процесс уже не используется, то его можно удалить. Все экземпляры шагов рабочего процесса, определенные в рабочем процессе, должны иметь статус **Завершено**.

> [!CAUTION]
> При удалении рабочего процесса все сведения в рабочем процессе утрачиваются.

На странице **Рабочий процесс** создайте рабочий процесс, указав в строках связанные с ним шаги. Каждый шаг состоит из события рабочего процесса, ограниченного условиями события, и отклика рабочего процесса, ограниченного параметрами отклика. Шаги рабочего процесса заполняются посредством заполнения полей в строках рабочего процесса с использованием фиксированных списков значений события и отклика, представляющих сценарии, которые поддерживаются кодом приложения. Дополнительные сведения см. в разделе [Создание рабочих процессов утверждения](across-how-to-create-workflows.md).

## <a name="delete-a-workflow" />Удаление рабочего процесса

1. Выберите значок ![Лампочка, которая открывает функцию «Что вы хотите сделать»](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Рабочие процессы**, затем выберите связанную ссылку.
2. Выберите рабочий процесс, который требуется удалить.
3. Выберите действие **Удалить**.
4. Также можно открыть рабочий процесс, который требуется удалить.
5. На странице **Рабочий процесс** выберите действие **Удалить**.

> [!NOTE]
> Удаление рабочего процесса требует его отключения. Чтобы отключить рабочий процесс, откройте его на странице **Рабочие процессы**, затем выключите переключатель **Включено**.

## <a name="see-also" />См. также

[Создание рабочих процессов утверждения](across-how-to-create-workflows.md)  
[Включение рабочих процессов утверждения](across-how-to-enable-workflows.md)  
[Использование рабочих процессов утверждения](across-use-workflows.md)  
[Просмотр архивированных экземпляров шагов рабочих процессов](across-how-to-view-archived-workflow-step-instances.md)  
[Пошаговое руководство. Настройка и использование рабочего процесса утверждения покупки](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Настройка рабочих процессов утверждения](across-set-up-workflows.md)  
[Рабочий процесс](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
