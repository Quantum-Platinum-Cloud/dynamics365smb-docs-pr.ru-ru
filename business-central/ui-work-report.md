---
title: Выполнение и печать отчетов
description: 'Узнайте, как вводить отчет в очередь заданий и планирование его обработки в конкретные дату и время.'
author: jswymer
ms.topic: conceptual
ms.search.keywords: 'task, process, report, print, schedule, save, Excel, PDF, Word, dataset'
ms.search.form: null
ms.date: 09/09/2022
ms.author: jswymer
---
# <a name="run-and-print-reports" />Выполнение и печать отчетов

Отчет собирает информацию на основе указанного набора критериев. Он систематизирует и представляет информацию в удобном для чтения формате, который вы можете распечатать или сохранить в виде файла. Предусмотрено много отчетов, к которым можно получить доступ с помощью приложения. Отчеты обычно содержат сведения относительно контекста страницы, на которой вы находитесь. Например, страница **Клиент** включает отчеты "10 лучших клиентов", "Статистика продаж" и т. п.

> [!NOTE]
> Пакетные задания и XMLport более или менее аналогичны отчетам, но используются больше для обработки экспорта данных. Поэтому, например, пакетное задание **Создать напоминания** создает документы-напоминания для отправки клиентам с просроченными платежами. В этой статье в основном упоминаются "отчеты", но аналогичная информация относится к пакетным заданиям и XMLport.

## <a name="get-started" />Начать

Отчеты можно найти в меню **Отчеты** на выбранных страницах, списках и карточках или можно использовать поиск ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") для поиска отчетов по имени. Для обзора встроенных отчетов, которые вы можете использовать в [!INCLUDE[prod_short](includes/prod_short.md)], отсортированных по категориям, см. раздел [Доступные отчеты в [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md).

При выборе отчета обычно отображается страница запроса, &mdash; с названием в соответствии с именем отчета, &mdash; позволяющая настроить различные параметры и фильтры, которые определяют включаемые данные. В следующих разделах объясняется, как использовать страницу запроса для создания, предварительного просмотра и печати отчета.

## <a name="a-namesavedsettingsausing-default-valuesmdashpredefined-settings" /><a name="SavedSettings"></a>Использование значений по умолчанию &mdash; предопределенные настройки

Большинство страниц запросов отчетов включают поле **Использовать значения по умолчанию из**. С этим полем можно выбрать предопределенные настройки для отчета, которые автоматически устанавливают параметры и фильтры. Выберите запись из раскрывающегося списка, чтобы увидеть, как параметры и фильтры на странице запроса изменятся соответствующим образом.

Всегда доступна запись **Последние использованные параметры и фильтры**. Эта операция задает в отчете использование параметров и фильтров, которые использовались при последнем использовании отчета.

В поле **Использовать значения по умолчанию из** обеспечивает быстрый и надежный способ создания отчетов, содержащих правильные данные. После выбора записи вы можете изменить любые параметры и фильтры перед предварительным просмотром или печатью отчета. Внесенные изменения не будут сохранены в выбранной операции предопределенных настроек, но будут сохранены в операции **Последние использованные параметры и фильтры**.

> [!NOTE]
> Стандартные настройки обычно устанавливаются и управляются администратором. Узнайте больше в разделе [Управление сохраненными настройками отчетов и пакетных заданий](reports-saving-reusing-settings.md).

## <a name="specifying-the-data-to-include-in-a-report" />Определение данных для включения в отчет

Используйте поля в **Параметры** и **Фильтры** для изменения или ограничения информации, которую вы хотите в отчете. Фильтры в отчете можно устанавливать примерно так же, как фильтры в списках. Подробнее см. в разделе [Фильтрация](ui-enter-criteria-filters.md#filtering).

> [!CAUTION]
> Экспресс-вкладка **Фильтр** на странице запроса отчета предоставляет общие возможности фильтрации для отчетов. Эти фильтры являются необязательными.
>
> Некоторые отчеты игнорируют любые такие фильтры, то есть выходные данные отчета не зависят от фильтра, заданного на экспресс-вкладке **Фильтр**. Невозможно предоставить список того, какие поля игнорируются в каких отчетах, поэтому вам придется экспериментировать с фильтрами при их использовании.
>
> **Пример**. При использовании пакетного задания **Создать напоминания** фильтр для поля **Книга операций по клиентам** для **Уровень последнего учтенного напоминания** игнорируется, поскольку фильтры являются фиксированными для данного пакетного задания.

## <a name="previewing-a-report" />Предварительный просмотр отчета

С помощью предварительного просмотра отчета можно увидеть, как он будет выглядеть, перед его печатью. Предварительный просмотр не зависит от выбранного принтера в поле **Принтер** на странице запроса. Он контролируется браузером. После предварительного просмотра вы можете вернуться на страницу запроса и внести необходимые изменения в параметры и фильтры.

Варианты предварительного просмотра на странице **Запрос отчета** зависят от отчета. Поэтому для некоторых отчетов вы можете выбрать **Предварительный просмотр**, а для других выбрать **Предварительный просмотр и закрытие**. Обе варианта открывают предварительный просмотр отчета. Разница в том, что **Предварительный просмотр** оставляет страницу запроса открытой, поэтому вы можете вернуться к ней, внести изменения, повторно просмотреть или распечатать. Напротив, с **Предварительный просмотр и закрытие** страница запроса закрывается и вам придется снова открыть отчет, чтобы внести изменения или распечатать.

> [!NOTE]
> Если вы используете Business Central выпуска 2020 волны 1 или более раннюю версию, доступен только один вариант **Предварительный просмотр**, закрывающий страницу запроса при предварительном просмотре, как описано выше для варианта **Предварительный просмотр и закрытие**.

### <a name="work-with-the-preview" />Работа с предварительным просмотром

В предварительном просмотре используйте строку меню в окне предварительного просмотра отчета для выполнения следующих действий:

- Переход по страницам
- Увеличение и уменьшение
- Изменение размеров по размеру страницы
- Выберите текст

    Можно копировать текст из отчетов, затем вставлять его в другие места, такие как страница в [!INCLUDE[prod_short](includes/prod_short.md)] или в Microsoft Word. Например, с помощью мыши вы выбираете левую кнопку мыши и удерживаете то место, где хотите начать. Сдвиньте мышь, чтобы выбрать одно или несколько слов, предложений или абзацев. Затем нажмите правую кнопку мыши и выберите **Копировать**. Теперь выбранный текст можно вставить в требуемом месте.
- Сдвиньте документ

    Можно переместить видимую область отчета в любом направлении, чтобы просмотреть другие области отчета. Панорамирование удобно, если отчет был увеличен для просмотра подробных сведений. Например, при использовании мыши, выберите и удерживайте левую клавишу мыши в любом месте предварительного просмотра отчета и перемещайте мышь, чтобы выбрать раздел отчета.

- Загрузка в PDF-файл на компьютере или в сети.
- Печать

## <a name="saving-a-report-to-a-file" />Сохранение отчета в файл

Можно сохранить отчет в PDF-документ, документ Microsoft Word, книгу Microsoft Excel или документ XML, выбрав пункт **Отправить**, затем выбрав нужный вариант. Файл загружается на ваше устройство.

Если ваша организация настроила OneDrive для системных функций, книги Excel и документы Word не загружаются, а открываются в браузере с помощью Excel или Word для Интернета.

> [!TIP]
> Параметры **Документ Microsoft Excel (только данные)** и **XML-документ** в основном для сложных целей. Обычно вы используете эти параметры для подробного анализа данных. Подробнее см. в разделе [Анализ данных отчета с помощью Excel и XML](report-analyze-excel.md).
>
> Вы также можете использовать **Документ Microsoft Excel (только данные)** для создания новых макетов Excel для данного отчета. Подробнее см. в разделе [Работа с макетами Excel](ui-excel-report-layouts.md).  

## <a name="a-nameschedulereporta-scheduling-a-report-to-run-later-or-periodically" /><a name="ScheduleReport"></a> Планирование выполнения отчета позднее или периодически

Можно запланировать одиночный или повторяющийся отчет для выполнения в заданную дату и время. Спланированные отчеты вводятся в очередь заданий и обрабатываются в намеченное время, как и другие задания. Выберите параметр **Запланировать** после выбора **Отправить**, затем введите такую информацию, как принтер, время и дата. Отчет добавляется в очередь заданий и выполняется в указанное время. Если отчет обработан, элемент удаляется из очереди заданий. Подробнее см. в разделе [Использование очередей работ для планирования задач](admin-job-queues-schedule-tasks.md).  

Когда вы планируете выполнить отчет, вы можете указать, например, что он должен выполняться каждый четверг, установив поле **Формула даты следующего запуска** на *D4*. Подробнее см. в разделе [Использование формул дат](ui-enter-date-ranges.md#use-date-formulas).  

Можно сохранить отчет в файле (таком как Excel, Word или PDF), напечатать его или только создать отчет. Если выбрано сохранить отчет в файл, обработанный отчет отправляется на страницу **Входящие отчеты** в вашем ролевом центре для просмотра. Узнайте больше в разделе [Совместное использование и экспорт отчетов с помощью папки «Входящие отчеты»](ui-work-report-inbox.md)

### <a name="manage-scheduled-recurring-reports" />Управление запланированными повторяющимися отчетами

Запланированные отчеты генерируются пакетными заданиями, управляемыми на странице **Записи очереди заданий**. Вы можете увидеть статус и другую информацию для каждого отчета на странице, приостановить/возобновить пакетное задание отчетов и создать отчет по требованию.

На странице **Записи очереди заданий** вы также можете изменить некоторые параметры отчета, такие как тип выходного файла, периодичность, дата выполнения, а также время начала и окончания. Однако перед редактированием существующего запланированного отчета необходимо приостановить очередь заданий отчета:

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать 1.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Операции очереди работ**, затем выберите связанную ссылку.  
2. На странице **Операции очереди работ** выберите требуемый отчет.
3. Выберите действие **Поставить на удержание**.
4. Откройте и отредактируйте запланированный отчет, выбрав его статус (*На удержании*).

После редактирования параметров отчета повторите первые два шага, а затем выберите действие **Установить статус «Готово»** для возобновления формирования отчета.

Узнайте больше об управлении очередью заданий в разделе [Использование очереди заданий для планирования задач](admin-job-queues-schedule-tasks.md).  

## <a name="a-nameprintreportaprinting-a-report" /><a name="PrintReport"></a>Печать отчета

Для печати отчета выберите **Печать** на странице запроса отчета или в строке меню на странице **Предварительный просмотр**.

Если в отчете используется макет Excel, вы не увидите поле **Принтер** или кнопки **Печать** или **Предварительный просмотр**. Вместо этого есть параметр **Загрузить**. Для печати выберите **Загрузить**, затем откройте загруженный файл в Excel и распечатайте оттуда.

### <a name="a-nameprinteraprinter" /><a name="Printer"></a>Принтер

Поле **Принтер** на странице запроса содержит название принтера, на который отправляется отчет. Чтобы сменить принтер, просто выберите принтер из списка.

> [!NOTE]
> Параметр **(Обрабатывается браузером)** означает, что для отчета не назначен принтер. В этом случае браузер обрабатывает распечатку и отображает стандартные шаги печати, где вы можете выбрать локальный принтер, подключенный к вашему устройству. Параметр **(Обрабатывается браузером)** недоступен в мобильном приложении [!INCLUDE[prod_short](includes/prod_short.md)] или приложении для Microsoft Teams.

> [!TIP]
> Принтер, выбранный по умолчанию, настраивается на странице **Выбор принтера**. Подробнее об изменении принтера по умолчанию см. в разделе [Настройка принтеров по умолчанию](ui-specify-printer-selection-reports.md#default).

### <a name="printing-reports-in-thai" />Печать отчетов в Таиланде

Конкретно в тайской версии [!INCLUDE[prod_short](includes/prod_short.md)] кнопка **Печать** не может правильно печатать отчеты из-за ограничений в службе, которая формирует пригодный для печати PDF-файл. Вместо этого, можно открыть в отчет в Word, затем сохранить его как печатаемый PDF.  

Или можно попросить администратора создать макет отчета Word для наиболее часто используемых отчетов. Подробнее см. в разделе [Управление макетами отчетов и документов](ui-manage-report-layouts.md).  

## <a name="switching-the-report-layout" />Переключение макета отчета

Макет отчета определяет, что отображается в отчете, как он скомпонован и в каком стиле. Существует несколько способов изменить макет:

- Когда вы настраиваете запуск отчета, вы увидите текущий макет в поле **Макет отчета** на странице запроса. Чтобы временно переключиться на другой макет, выберите поле **Макет отчета**, затем выберите из списка доступных макетов для отчета.
- Чтобы изменить макет по умолчанию, используемый отчетом, перейдите на страницы **Макеты отчетов** или **Выбор макета отчета**.

Подробнее см. в разделе [Установка макета, используемого отчетом](ui-set-report-layout.md). Или, если вы хотите настроить свой собственный макет отчета, перейдите в раздел [Приступайте к созданию макетов](ui-get-started-layouts.md).

## <a name="change-language-and-format-of-numbers-dates-and-times" />Изменение языка и формата чисел, дат и времени

По умолчанию язык текста, а также формат чисел, дат и времени в отчете основаны на вашем рабочем языке и региональных настройках, которые определены на странице **Мои настройки**. Однако вы можете изменить язык и регион формата в каждом конкретном случае при предварительном просмотре, выводе на печать или отправке отчета. На странице запроса выберите **Дополнительно**, после чего задайте параметры **Язык** и **Регион формата**.

Для получения дополнительной информации о странице **Мои настройки** перейдите к разделу [Изменение базовых настроек](ui-change-basic-settings.md#region).

## <a name="advanced-options" />Дополнительные параметры

Поля на экспресс-вкладке **Дополнительно** задают ограничения для создаваемого отчета для управления ресурсами принтера. Обычно вам не нужно менять эти настройки, если у вас нет большого отчета. Если отчет превышает эти ограничения при попытке предварительного просмотра или печати, сообщение укажет, какое ограничение было превышено. Затем вы можете изменить настройки в соответствии с вашим отчетом. Однако каждое поле имеет максимальное значение, о котором вам следует знать:

|Поле|Максимальное значение|
|-----|-------------|
|Максимальное время отрисовки|12:00:00|
|Максимальное количество строк|1000 000|
|Максимальное количество документов|500|

> [!NOTE]
> Максимальные значения могут быть разными для [!INCLUDE[prod_short](includes/prod_short.md)] (локальная версия), и администратор может их изменить. Подробнее см. в разделе [Настройка Business Central Server — отчеты](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#Reports). Для обзора ограничений отчетов в [!INCLUDE[prod_short](includes/prod_short.md)] (онлайн) см. раздел [Операционные ограничения](/dynamics365/business-central/dev-itpro/administration/operational-limits-online).

## <a name="see-related-microsoft-trainingtrainingpathssetup-reporting-dynamics-365-business-central" />См. соответствующее [обучение Microsoft](/training/paths/setup-reporting-dynamics-365-business-central/).

## <a name="see-also" />См. также

[Доступные отчеты в [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md)  
[Используйте отчеты в повседневной работе](reports-use-reports.md)  
[Обзор бизнес-аналитики и отчетности](reports-bi-reporting.md)  
[Настройка принтеров](ui-specify-printer-selection-reports.md)  
[Запуск пакетных заданий и XMLport](ui-how-run-batch-jobs.md)  
[Работа с календарными датами и значениями времени](ui-enter-date-ranges.md)  
[Управление макетами отчетов и документов](ui-manage-report-layouts.md)  
[Финансовая бизнес-аналитика](bi.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
