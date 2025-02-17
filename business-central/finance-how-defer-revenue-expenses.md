---
title: Доходы и расходы будущих периодов
description: 'Для признания доходов и расходов в периодах, когда транзакция не была учтена, можно использовать функцию автоматического отнесения доходов и расходов по указанному графику.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: postpone
ms.search.form: '1700, 1701, 1702, 1703, 1704, 1705, 1706, 1707'
ms.date: 06/16/2021
ms.author: edupont
---
# <a name="defer-revenues-and-expenses" />Доходы и расходы будущих периодов

Для выявления дохода или расхода в периоды, отличные от периода, в котором транзакция была учтена, можно использовать функцию автоматического отнесения доходов и расходов по указанному графику.

Чтобы распределять доходы или расходы на соответствующие отчетные периоды, требуется настроить шаблон РБП для ресурса, товара или счета ГК, для которых будет учитываться доход или расход. При учете связанного документа продажи или покупки доходы или расходы относятся к соответствующим учетным периодам в соответствии с графиком отнесения, который определяется настройками в шаблоне РБП и датой учета.

## <a name="to-set-up-a-gl-account-for-deferral" />Настройка счета ГК для РБП

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **План счетов**, а затем выберите связанную ссылку.
2. Выберите действие **Создать**.
3. Требуемым образом заполните поля, чтобы создать счет ГК для доходов будущих периодов. Дополнительные сведения см. в разделе [Главная книга и план счетов](finance-general-ledger.md).
4. Повторите шаги 2 и 3, чтобы создать новый счет ГК для расходов будущих периодов.

Для обоих типов будущих периодов выберите **Балансовый отчет** в поле **Тип** и задайте соответствующие названия счетов, например "Незаработанные доходы" для доходов будущих периодов и "Неоплаченные расходы" расходов будущих периодов.

## <a name="to-set-up-a-deferral-template" />Настройка шаблона РБП

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Шаблоны РБП**, а затем выберите связанную ссылку.
2. Выберите действие **Создать**.
3. Заполните соответствующим образом поля.
4. В поле **Метод расчета** укажите, как рассчитывается поле **Сумма** для каждого периода на странице **Расписание РБП**. Можно выбирать из следующих параметров:

   * **Линейный**: периодические суммы РБП рассчитываются согласно числу периодов, распределенные в соответствии с длительностью периода.
   * **Равномерно по периодам**: периодические суммы РБП рассчитываются согласно числу периодов, распределенные равномерно по периодам.
   * **Дни по периодам**: периодические суммы РБП рассчитываются согласно числу дней в периоде.
   * **Определяется пользователем**: периодические суммы РБП не рассчитываются. Необходимо вручную ввести значения в поле **Сумма** за каждый период на странице "Расписание РБП". Дополнительные сведения см. в разделе "Изменение расписания РБП из счета продажи".
5. В поле **Описание периода** укажите описание, которое будет отображаться в операциях, предназначенных для учета как РБП. Можно ввести следующие коды места заполнения для типичных значений, которые будут автоматически вставлены при отображении описания периода.

   * %1 = номер дня даты учета периода
   * %2 = номер недели даты учета периода
   * %3 = номер месяца даты учета периода
   * %4 = название месяца даты учета периода
   * %5 = название учетного периода даты учета периода
   * %6 = финансовый год даты учета периода

Пример: дата учета 06.02.2016. Если введено "Расходы, отложенные на %4 %6", будет отображаться описание "Расходы, отложенные на февраль 2016".

## <a name="to-assign-a-deferral-template-to-an-item" />Присвоение шаблона РБП товару

> [!NOTE]  
> Шаги в этой процедуре такие же, как при назначении шаблона РБП счету главной книги или ресурсу.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Товар**, а затем выберите связанную ссылку.
2. Откройте карточку товара, для которого необходимо отложить доходы или расходы на учетные периоды, когда товар был продан или приобретен.
3. В поле **Шаблон РБП по умолчанию** выберите соответствующий шаблон РБП.

## <a name="to-change-a-deferral-schedule-from-a-sales-invoice" />Изменение расписания РБП из счета продажи

> [!NOTE]  
> Шаги в этой процедуре совпадают с шагами при изменении расписания РБП для расходов из счета покупки.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Счета продажи**, а затем выберите связанную ссылку.
2. Создайте счет продажи для товара, у которого есть назначенный шаблон РБП. Дополнительные сведения см. в разделе [Выставление счетов продажи](sales-how-invoice-sales.md).

    Обратите внимание, что сразу же после ввода товара (или ресурса либо счета ГК) в строке счета в поле **Код РБП** заносится код из назначенного шаблона РБП.
3. Выберите действие **Расписание РБП**.
4. На странице **Расписание РБП** измените настройки в заголовке или значения в строках, например чтобы отнести сумму на дополнительный учетный период.
5. Выберите действие **Рассчитать план**.
6. Нажмите кнопку **ОК**. Расписание РБП обновляется для счета продажи. Соответствующий шаблон РБП не изменяется.

## <a name="to-preview-how-deferred-revenues-or-expenses-will-be-posted-to-the-general-ledger" />Предварительный просмотр того, как доходы или расходы будущих периодов будут учтены в главной книге

> [!NOTE]  
> Шаги в этой процедуре совпадают с шагами процедуры предварительного просмотра учета расходов будущих периодов.

1. На странице **Счет продажи** выберите действие **Предварительный просмотр учета**.
2. На странице **Предварительный просмотр учета** выберите действие **Операция ГК**, затем выберите действие **Показать связанные операции**.

Операции ГК, которые будут учтены на указанном счете будущего периода, например "Незаработанные доходы", обозначаются описанием, введенным в поле **Описание периода** в шаблоне РБП, например "Расходы, отложенные на февраль 2016".

## <a name="to-review-posted-deferrals-in-the-sales-deferral-summary-report" />Просмотр учтенных РБП в отчете "Сводка РБП по продажам"

> [!NOTE]  
> Шаги в этой процедуре совпадают с шагами процедуры просмотра отчета "Сводка РБП по покупкам".

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Сводка РБП по продажам**, а затем выберите связанную ссылку.
2. На странице **Сводка РБП по продажам** в поле **Сальдо на дату** введите дату, по которую требуется просмотреть доходы будущих периодов.
3. Нажмите кнопку **Предварительный просмотр**.

## <a name="to-specify-a-period-in-which-to-allow-deferral-posting" />Задание периода, в котором разрешен учет расходов/доходов будущих периодов

Вы можете указать период, в течение которого пользователи могут учитывать транзакции, путем ввода дат в поля **Разрешить учет с** и **Разрешить учет по** следующим образом:

* Для всех пользователей на странице **Настройка ГК**
* Для конкретных пользователей на странице **Настройка пользователя**

Если вы это сделали, вы должны сделать исключение для расходов/доходов будущих периодов, чтобы разрешить их учет вне этого периода. Чтобы задать период, выполните следующие действия.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") введите **Настройка ГК** или **Настройка пользователя**, а затем выберите соответствующую ссылку.
2. В полях **Разрешить учет РБП с** и **Разрешить учет РБП по** введите дату начала и окончания периода.

## <a name="see-related-microsoft-trainingtrainingmodulesprocessing-invoices-dynamics-365-business-central" />См. соответствующее [обучение Microsoft](/training/modules/processing-invoices-dynamics-365-business-central/)

## <a name="see-also" />См. также

[Финансы](finance.md)  
[Настройка финансов](finance-setup-finance.md)  
[Работа с финансовыми журналами](ui-work-general-journals.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
