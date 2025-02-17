---
title: Очистка данных с помощью политик хранения
description: 'Вы можете указать, как часто вы хотите удалять определенные типы данных.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'delete, data, retention, policy, policies'
ms.search.form: '3903, 3901'
ms.date: 04/01/2021
ms.author: bholtorf
---
# <a name="define-retention-policies" />Определение политик хранения
Администраторы могут определять политики хранения, чтобы указать, как часто они хотят, чтобы [!INCLUDE[prod_short](includes/prod_short.md)] удалял устаревшие данные в таблицах, содержащих записи журнала и архивные записи. Например, очистка записей журнала может упростить работу с действительно важными данными. Политики могут включать все данные в таблицах, срок действия которых истек, или вы можете добавить критерии фильтрации, которые будут включать в политику только определенные просроченные данные. 

## <a name="required-setups-and-permissions" />Обязательные настройки и разрешения
До начала работы с политиками хранения необходимо настроить следующее.

|Настройка  |Описание  |
|---------|---------|
|**Допустимые таблицы**     |Мы предоставляем список таблиц, которые могут быть включены в политики хранения. Однако, если вы хотите добавить таблицы из расширения в политику хранения, разработчик должен добавить свои таблицы в список. Для получения дополнительной информации см. [Включение вашего расширения в политику хранения](admin-data-retention-policies.md#including-your-extension-in-a-retention-policy-requires-help-from-a-developer).          |
|**Периоды хранения**     |Укажите периоды времени, в течение которых данные будут храниться в таблицах политики. Периоды определяют, как часто данные будут удаляться.         |

Кроме того, у вас должны быть разрешения пользователя SUPER или набор разрешений для настройки политики хранения. Пользователи, которым предоставлен набор разрешений установки политики хранения, могут определять политики хранения для таблиц, даже если у них нет разрешений на чтение и удаление для этих таблиц. Запись очереди заданий должна запускаться от имени пользователя с разрешениями на чтение и удаление данных. Мы рекомендуем не предоставлять набор разрешений «Настройка политики хранения» пользователям, которым не должно быть разрешено удалять данные.

> [!NOTE]
> Если вы используете [!INCLUDE[prod_short](includes/prod_short.md)] локально, и вы хотите опробовать политики хранения в демонстрационной базе данных Cronus, вам нужно сделать несколько вещей. Демонстрационная организация не содержит таблиц, которые можно использовать с политиками хранения, поэтому их необходимо добавить. Для этого создайте новую пустую компанию в демонстрационной базе данных. В новой компании импортируйте пакет конфигурации RapidStart для вашей страны, соответствующий стандартному пакету NAV17.0.W1.ENU.STANDARD.rapidstart. Данные о настройке политик хранения будут доступны в новой компании.

### <a name="to-create-retention-periods" />Для создания периодов хранения
Срок хранения может быть сколь угодно длинным или коротким. Чтобы создать период хранения, на странице **Политики хранения** используйте действие **Период хранения**. Определенные вами периоды будут доступны для всех политик.

> [!NOTE]
> Из соображений соответствия мы определили минимальный срок хранения для некоторых таблиц. Если вы установите срок хранения, который меньше необходимого минимума, в сообщении будет отображаться обязательный период.

### <a name="set-up-a-retention-policy" />Настройка политики хранения
1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Политики хранения**, а затем выберите связанную ссылку.
2. В поле **Код таблицы** выберите таблицу, которую предполагается включить в политику.
3. В поле **Период хранения** укажите продолжительность хранения данных в таблице.
4. Необязательно: чтобы применить политику к определенным данным в таблице, выключите переключатель "Применить ко всем записям". Отобразится экспресс-вкладка «Политика хранения записей», где вы можете установить фильтры для создания подмножеств данных для каждой строки. Дополнительные сведения см. в разделе [Фильтрация](ui-enter-criteria-filters.md#filtering).

   > [!NOTE]
   > У каждой строки свой срок хранения. Если вы укажете разные периоды хранения для одних и тех же данных, будет использоваться самый длинный период. Кроме того, в некоторых таблицах есть фильтры, которые нельзя изменить или удалить. Чтобы помочь вам идентифицировать эти фильтры, они отображаются более светлым шрифтом.

## <a name="applying-retention-policies" />Применение политик хранения
Вы можете использовать запись в очереди заданий, чтобы применить политики хранения для автоматического удаления данных, или вы можете применить политики вручную.

Чтобы применить политику хранения автоматически, просто создайте и включите политику. Когда вы включаете политику, мы создаем запись в очереди заданий, которая будет применять политики хранения в соответствии с указанным вами периодом хранения. Все политики хранения будут использовать одну и ту же запись очереди заданий. По умолчанию запись в очереди заданий применяет политику каждый день в 2:00. Вы можете изменить значение по умолчанию, но если вы это сделаете, мы рекомендуем его запускать в нерабочее время. Дополнительные сведения см. в разделе [Использование очередей работ для планирования задач](admin-job-queues-schedule-tasks.md). 

Вы можете вручную применить политику, используя действие **Применить вручную** на странице **Политики хранения**. Если вы хотите всегда применять политику вручную, включите переключатель **Вручную**. Запись в очереди заданий игнорирует политику при запуске.

## <a name="viewing-retention-policy-log-entries" />Просмотр записей журнала политики хранения
Вы можете просмотреть действия, связанные с политиками хранения, на странице **Журнал политик хранения**. Например, записи создаются при применении политики или при возникновении ошибок. 

## <a name="including-your-extension-in-a-retention-policy-requires-help-from-a-developer" />Включение вашего расширения в политику хранения (требуется помощь разработчика)
По умолчанию политики хранения охватывают только таблицы, включенные в список таблиц [!INCLUDE[prod_short](includes/prod_short.md)], которые мы предоставляем. Вы можете удалить таблицы по умолчанию из списка и добавить собственные таблицы. То есть вы не можете добавить таблицу, которую не создали сами. Например, вы не можете добавлять другие таблицы из [!INCLUDE[prod_short](includes/prod_short.md)] или из расширения, которое вы приобрели.

Чтобы добавить ваши таблицы в список разрешенных таблиц, разработчик должен добавить некоторый код, например, в codeunit установщика для расширения (codeunit с подтипом *установить*). 

Когда разработчик добавляет таблицу, он может указать обязательные фильтры и фильтры по умолчанию. Обязательные фильтры нельзя удалить или изменить позже, когда вы добавляете таблицы для определения политики хранения. Фильтры по умолчанию — это просто дружеские предложения.

Ниже приведены примеры того, как добавить таблицу в список разрешенных таблиц с обязательными фильтрами или фильтрами по умолчанию и без них. Для более сложного примера см. codeunit 3999 "Пол. Хран. Установить — BaseApp". 

```al
 trigger OnInstallAppPerCompany()
    var
        RetenPolAllowedTables: Codeunit "Reten. Pol. Allowed Tables";
    begin
        RetenPolAllowedTables.AddAllowedTable(Database::"Retention Policy Log Entry");
    end;
```

Следующий пример включает обязательный фильтр.

```al
 trigger OnInstallAppPerCompany()
    var
        ChangeLogEntry: Record "Change Log Entry";
        RetenPolAllowedTables: Codeunit "Reten. Pol. Allowed Tables";
        RetentionPeriod: Enum "Retention Period Enum";
        RecRef: RecordRef;
        TableFilters: JsonArray;
        Enabled: Boolean;
        Mandatory: Boolean;
    begin
        ChangeLogEntry.Reset();
        ChangeLogEntry.SetFilter("Field Log Entry Feature", '%1|%2', ChangeLogEntry."Field Log Entry Feature"::"Monitor Sensitive Fields", ChangeLogEntry."Field Log Entry Feature"::All);
        RecRef.GetTable(ChangeLogEntry);
        Enabled := true;
        Mandatory := true;
        RetenPolAllowedTables.AddTableFilterToJsonArray(TableFilters, RetentionPeriod::"28 Days", ChangeLogEntry.FieldNo(SystemCreatedAt), Enabled, Mandatory, RecRef);
        RetenPolAllowedTables.AddAllowedTable(Database::"Change Log Entry", ChangeLogEntry.FieldNo(SystemCreatedAt), TableFilters);
    end;
```

После того, как разработчик добавил таблицы в список, администратор может включить их в политику хранения. 

## <a name="see-also" />См. также

[Анализ телеметрии трассировки политики хранения](/dynamics365/business-central/dev-itpro/administration/telemetry-retention-policy-trace)  
[Изменение аудита в Business Central](across-log-changes.md)  
[Фильтрация](ui-enter-criteria-filters.md#filtering)  
[Использование очередей работ для планирования задач](admin-job-queues-schedule-tasks.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
