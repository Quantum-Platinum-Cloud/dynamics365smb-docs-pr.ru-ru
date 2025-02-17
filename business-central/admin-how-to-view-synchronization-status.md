---
title: Просмотр статуса заданий синхронизации (содержит видео)
description: 'Используйте страницу Ошибки синхронизации связанных данных для просмотра состояния заданий синхронизации, которые были выполнены для связанных записей в интеграции.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'sales, crm, integration, sync, synchronize'
ms.search.form: 6250
ms.date: 06/14/2021
ms.author: bholtorf
---

# <a name="view-the-status-of-synchronization-jobs" />Просмотр статуса заданий синхронизации


Используйте страницу **Ошибки синхронизации связанных данных** для просмотра состояния заданий синхронизации, которые были выполнены для связанных записей в интеграции Dataverse или [!INCLUDE[crm_md](includes/crm_md.md)]. Сюда входят задания, запущенные из очереди заданий, и задания ручной синхронизации, выполненные для записей из [!INCLUDE[prod_short](includes/prod_short.md)]. Например, просмотр их статуса бывает полезен при устранении неполадок, поскольку он дает вам доступ к сведениям об ошибках, относящихся к связанным записям. Как правило, эти ошибки вызваны действиями пользователя, например, когда:  

* Два человека внесли изменения в одни и те же данные в обоих бизнес-приложениях.
* Кто-то удалил данные в одном из приложений, но не в обоих.

> [!Note]
> На странице **Ошибки синхронизации связанных данных** отображается информация о заданиях, относящихся к связанным записям. Если вы устраните все ошибки, но записи по-прежнему не синхронизируются, это может быть связано с настройкой интеграции. Как правило, такие ошибки устраняет администратор.   

## <a name="example" />Пример
В этом видео показан пример устранения ошибок, возникших при синхронизации с [!INCLUDE[prod_short](includes/cds_long_md.md)]. Процесс будет одинаковым для любой интеграции. 

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2097304]


## <a name="to-view-and-resolve-synchronization-errors-for-coupled-records" />Чтобы просмотреть и устранить ошибки синхронизации для связанных записей
1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок , введите **Ошибки синхронизации связанных данных**, а затем выберите связанную ссылку.
2. Страница **Ошибки синхронизации связанных данных** отображает проблемы, которые возникли при синхронизации связанных записей. В следующей таблице приведены действия, которые вы можете использовать для последовательного решения проблем:

|Действие|Описание|
|----|----|
|**Удалить связь**|Рассоединяет записи, и они больше не будут синхронизироваться. Чтобы возобновить синхронизацию, их нужно снова соединить. |
|**Повторить** и **Повторить все**|Для каждой записи, где обнаружена ошибка, синхронизация пропускается, если вы не исправите проблему. "Повтор" включит выбранную запись в следующую синхронизацию, а **Повторить все** включает все записи.|
|**Синхронизировать**|Приложение попытается разрешить конфликт, если данные были изменены в обоих бизнес-приложениях. Можно выбрать данные для использования.|
|**Восстановить записи** и **Удалить записи**|Это полезно, когда запись была удалена в одном из бизнес-приложений. Операция "Удалить записи" удаляет запись или строку в приложении, где она еще существует. Операция "Восстановить записи" воссоздает запись или строку в бизнес-приложении, где она была удалена.|

> [!NOTE]
> Чтобы уменьшить количество конфликтов, которые необходимо разрешить, вы можете настроить сопоставления таблиц интеграции для автоматического применения этих действий. Чтобы получить больше информации, см. [Сопоставление таблиц интеграции](admin-how-to-modify-table-mappings-for-synchronization.md#mapping-integration-tables).

## <a name="to-view-the-synchronization-log-for-a-specific-manually-synchronized-record" />Просмотр журнала синхронизации для конкретной (синхронизированной вручную) записи
1. Откройте, например, запись клиента, товара или любую другую запись, которая синхронизирует данные между [!INCLUDE[prod_short](includes/prod_short.md)] и Dataverse или [!INCLUDE[crm_md](includes/crm_md.md)].
2. Выберите действие **Журнал синхронизации** для просмотра журнала синхронизации для выбранной записи. Например, определенный клиент, которого вы синхронизировали вручную.

## <a name="remove-couplings-between-records" />Удаление связей между записями
Когда что-то пойдет не так с вашей интеграцией и вам нужно разъединить записи, чтобы прекратить их синхронизацию, вы можете сделать это для одной или нескольких записей за раз. Вы можете отменить связывание одной или нескольких записей со страниц списка или страницы **Ошибки синхронизации связанных данных**, выбрав одну или несколько строк и выбрав **Удалить связывание**. Вы также можете удалить все связывания для одного или нескольких сопоставлений таблиц на странице **Сопоставления таблиц интеграции**. 

Если объект с однонаправленным связыванием удален в [!INCLUDE[prod_short](includes/prod_short.md)], необходимо вручную удалить нарушенное связывание. Для этого на странице **Ошибки синхронизации связанных данных** выберите действие **Найти для удаленных**, а затем удалите связывания.

## <a name="see-also" />См. также
[Настройка учетных записей пользователей для интеграции с Dynamics 365 Sales](admin-setting-up-integration-with-dynamics-sales.md)  
[Использование Dynamics 365 Sales из Business Central](marketing-integrate-dynamicscrm.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
