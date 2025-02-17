---
title: Подсчет и корректировка запасов
description: 'Описывает, как подсчитывать физические запасы и использовать документы инвентаризации для корректировки запасов в наличии.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'adjustment, status, negative, positive, increase, decrease, inventory'
ms.search.forms: '5895, 6561, 6562, 6563, 6564, 6565, 6566, 5892, 5891, 5879, 5880, 5893, 5897, 5882, 5881, 5899, 5875, 5878, 5877, 5876, 5896, 6567, 6568, 6569, 6570, 6571, 6572, 5883, 5886, 884, 5898, 5885, 5890, 5888, 5889, 5887, 5894, 6774, 6775, 6776, 6780, 6781, 6782, 6783'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="count-and-adjust-inventory-using-documents" />Подсчет и корректировка запасов с использованием документов

Можно выполнять физическую инвентаризацию товаров с помощью документов заказа инвентаризации и записи инвентаризации. Страница **Заказ инвентаризации** используется для организации проекта полной инвентаризации, например по каждому складу. Страница **Запись физической инвентаризации** используется для сообщения и фиксации фактической инвентаризации товаров. Можно создать несколько записей для одного заказа, например, чтобы распределить группы товаров по различным сотрудникам.

Отчет **Запись инвентаризации** может быть распечатан из каждой записи и содержит пустые поля количества для ввода инвентаризированных запасов. Когда пользователь завершил инвентаризацию и значения количества введены на странице **Запись инвентаризации**, выберите действие **Готово**. Это переводит количества в соответствующие строки на странице **Заказ инвентаризации**. Функция гарантирует, что никакая инвентаризация товаров не будет записана дважды.  

> [!NOTE]
> Использование документов для выполнения физической инвентаризации обеспечивает дополнительный контроль и поддерживает распределение инвентаризации на несколько сотрудников. Можно также выполнить задачу с использованием журналов, такие как страницы **Журналы инвентаризации** и **Журнал инвентаризации склада**. Дополнительные сведения см. в разделе [Подсчет, корректировка и повторная классификация запасов с помощью журналов](inventory-how-count-adjust-reclassify.md). В этой статье описывается, как выполнить физическую инвентаризацию с использованием документов.
>
> Если вы используете зоны, вы не можете использовать заказы на физическую инвентаризацию. Вместо этого используйте страницу **Журнал инвентаризации склада** для инвентаризации складских записей перед их синхронизацией с записями книги товаров.

Инвентаризация с помощью документов состоит из следующих этапов:

1. Создайте заказ инвентаризации с уже заполненными ожидаемыми количествами товаров.
2. Создайте одну или несколько записей инвентаризации из заказа.
3. Введите подсчитанные значения количества товаров в записи, как указано, например, в распечатках, и задайте значение **Завершен**.
4. Завершите и выполните учет заказа инвентаризации.

## <a name="to-create-a-physical-inventory-order" />Создание заказа инвентаризации

Заказ инвентаризации представляет собой готовый документ, который состоит из заголовка заказа инвентаризации и некоторых строк заказа инвентаризации. Информация в заголовке инвентаризации описывает, как выполнять инвентаризацию. Строки заказа инвентаризации содержат информацию о товарах и их местонахождении.

Для создания строк заказа инвентаризации обычно используется функция **Рассчитать строки** для отражения текущих запасов в виде строк заказа. Кроме того, можно использовать функцию **Копировать из документа**, чтобы заполнить строки содержимым другого открытого или учтенного заказа инвентаризации. В следующей процедуре описывается только использование функции **Рассчитать строки**.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Заказы инвентаризации**, а затем выберите связанную ссылку.
2. Выберите действие **Создать**.
3. Заполните требуемые поля на экспресс-вкладке **Общее**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Выберите действие **Рассчитать строки**.
5. Выберите требуемые параметры.
6. Установите фильтры, например, чтобы включить только подмножество товаров, подлежащих инвентаризации с первой записью.

    > [!TIP]
    > Чтобы запланировать для нескольких сотрудников инвентаризацию запасов, рекомендуется настроить различные фильтры при каждом использовании действия **Рассчитать строки**, чтобы заполнять заказ только подмножеством товаров запасов, который будет записывать этот пользователь. Затем при создании нескольких записей инвентаризации для нескольких сотрудников сводится к минимуму риск двойного учета товаров. Дополнительные сведения см. в разделе [Создание записи инвентаризации](#to-create-a-physical-inventory-recording).

7. Нажмите кнопку **ОК**.

Строка для каждого товара, который хранится на выбранном складе, в соответствии в заданными фильтрами и параметрами вставляется в заказ. Для товаров, которые настраиваются для трассировки товаров, установлен флажок **Использовать трассировку товара**, и сведения об ожидаемом количестве для серийных номеров и номеров партий доступны при выборе действия **Строки** и затем **Строки трассировки товаров**. Дополнительные сведения см. в разделе [Обработка отслеживания товаров при инвентаризации запасов](#handling-item-tracking-when-counting-inventory).

Теперь можно приступать к созданию одной или нескольких записей, которые являются инструкциям для сотрудников, который выполняют фактическую инвентаризацию.  

## <a name="to-create-a-physical-inventory-recording" />Создание записи инвентаризации

Для каждого заказа инвентаризации можно создать один или несколько документов записей инвентаризации, по которым сотрудники вводят подсчитанные количества, вручную или посредством интегрированного сканирующего устройства.

По умолчанию создается запись для всех строк соответствующего заказа инвентаризации. Чтобы исключить ситуацию, когда два сотрудника инвентаризируют один и тот же товар в случае распределенной инвентаризации, рекомендуется постепенно заполнять заказ инвентаризации путем задания фильтров пакетного задания **Рассчитать строки** (см. раздел "Создание заказа инвентаризации"), а затем создать запись инвентаризации с установленным флажком **Только строки, отсутствующие в записи**. Эти настройки обеспечивают, что каждая новая создаваемая запись содержит только товары, отличные от товаров в других записях.

В случае инвентаризации вручную можно напечатать список, отчет **Запись инвентаризации**, в котором имеется пустой столбец для записи подсчитанных количеств. После завершения инвентаризации вы вводите записанные количества в связанные строки на странице **Запись инвентаризации**. Наконец, вы переносите зарегистрированные количества в соответствующих заказ инвентаризации, задав статус **Завершен**.

1. На странице **Заказ инвентаризации**, на которой содержатся строки для товаров, которые необходимо сосчитать в одной записи, выберите действие **Создать новую запись**.
2. Выберите требуемые параметры и задайте фильтры.
3. Нажмите кнопку **ОК**.

    Создается документ записи инвентаризации.

4. Для каждого набора товаров для подсчета загрузите их в соответствующий заказ инвентаризации и повторите шаги с 1 по 3 с установленным флажком **Только строки, отсутствующие в записи**.

5. Выберите действие **Записи** для открытия страницы **Список записей инвентаризации**.
6. Откройте соответствующую запись.
7. На экспресс-вкладке **Общее** заполните необходимые поля.
8. Для товаров, использующих трассировку товаров, создайте дополнительную строку для каждого номера партии или кода серийных номеров, выбрав действие **Функции**, затем действие **Копировать строку**. Дополнительные сведения см. в разделе [Обработка отслеживания товаров при инвентаризации запасов](#handling-item-tracking-when-counting-inventory).  
9. Выберите действие **Печать**, чтобы подготовить физический документ, который сотрудники будут использовать для записи подсчитанных количеств.

## <a name="to-finish-a-physical-inventory-recording" />Завершение записи инвентаризации

Когда сотрудники сосчитали количества запасов, необходимо подготовиться за записи их в системе.

1. Со страницы **Список записей инвентаризации** выберите запись инвентаризации, которую требуется завершить, затем выберите действие **Правка**.
2. На экспресс-вкладке **Строки** заполните фактическое подсчитанное количество в поле **Количество** для каждой строки.
3. Для товаров с серийными номерам или номерами партий (установлен флажок **Использовать трассировку товаров**) введите подсчитанные количества в специальных строках для серийных номеров и номеров партий соответствующих товаров. Дополнительные сведения см. в разделе [Обработка отслеживания товаров при инвентаризации запасов](#handling-item-tracking-when-counting-inventory).
4. Установите флажок **Записано** в каждой строке.
5. После ввода всех данных для записи инвентаризации выберите действие **Готово**. Обратите внимание, что во всех строках должен быть установлен флажок **Записано**.

    > [!NOTE]
    > После завершения записи инвентаризации каждая строка перемещается в строку соответствующего заказа инвентаризации, которая ей точно соответствует. Для соответствия значения в полях **Код товара**, **Код варианта**, **Код склада** и **Код ячейки** должны быть одинаковыми в строках записи и заказа.<br /><br />
    > Если соответствующая строка заказа инвентаризации существует и если флажок **Разрешить запись без заказа** установлен, то новая строка вставляется автоматически и устанавливается флажок **Записано без заказа** в соответствующей строке заказа инвентаризации. В противном случае выводится сообщение об ошибке и процесс отменяется.<br /><br />
    > Если несколько строк записи инвентаризации соответствуют строке заказа инвентаризации, то отображается сообщение и процесс отменяется. Если по какой-либо причине две одинаковых строки инвентаризации попадают в заказ инвентаризации, можно использовать функцию для разрешения ситуации. Дополнительные сведения см. в разделе [Поиск повторяющихся строк заказа инвентаризации](#to-find-duplicate-physical-inventory-order-lines).

## <a name="to-complete-a-physical-inventory-order" />Завершение заказа инвентаризации

После завершения записи инвентаризации поле **Записанное кол-во (баз.)** в соответствующем заказе инвентаризации обновляется с подсчитанными (записанными) значениями и устанавливается флажок **В записи**. Если подсчитанное значение отличается от ожидаемого, это отличие отображается в полях **Полож. кол-во (баз.)** и **Отриц. кол-во (баз.)** соответственно.

Для просмотра ожидаемых количеств и любых записанных отличий для товаров с отслеживанием товара выберите действие **Строки**, затем выберите действие **Строки трассировки товара** для выбора различных представлений для серийных номеров и номеров партий, участвующих в подсчете запасов.

Также можно выбрать действие **Разница заказов инвентаризации** действие для просмотра возможных разниц между ожидаемым количеством и подсчитанным количеством.

### <a name="to-find-duplicate-physical-inventory-order-lines" />Поиск дублирующихся строк заказа инвентаризации

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Заказы инвентаризации**, а затем выберите связанную ссылку.
2. Откройте заказ инвентаризации, для которого требуется просмотреть дублирующиеся строки.
3. Выберите действие **Показать повторяющиеся строки**.

Отображаются повторяющиеся строки заказа инвентаризации, чтобы вы могли их удалить и оставить только одну строку с уникальным набором значений в полях **Номенклатурный номер**, **Код варианта**, **Код склада** и **Код ячейки**.

### <a name="to-post-a-physical-inventory-order" />Учет заказа инвентаризации

После завершения заказа инвентаризации и изменения его статуса на **Завершен** можно учесть его. Для заказа инвентаризации можно задать статус **Завершен** только в случае, если верно следующее:

- Все связанные записи инвентаризации имеют статус **Завершен**.
- Каждая строка заказа инвентаризации была сосчитана по крайней мере в одной строке записи инвентаризации.
- Флажки **В строках записей** и **Расчетное ожидаемое кол-во** были установлены для всех строк заказа инвентаризации.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Заказы инвентаризации**, а затем выберите связанную ссылку.
2. Выберите заказ инвентаризации, который требуется завершить, затем выберите действие **Изменить**.

    На странице **Заказ инвентаризации** можно просмотреть количество, зарегистрированное в поле **Записанное кол-во (баз.)**.
3. Выберите действие **Готово**.

    Поле **Статус** содержит значение **Завершено**, и теперь заказ можно изменить, только сначала выбрав действие **Открыть повторно**.
4. Для учета заказа выберите действие **Учет**, затем выберите кнопку **ОК**.

    Записи книги товаров будут обновлены вместе со всеми связанными записями трассировки товаров.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

### <a name="to-view-posted-physical-inventory-orders" />Просмотр учтенных заказов инвентаризации

После учета заказ инвентаризации будет удален и можно будет просмотреть и оценить документ как учтенный заказ инвентаризации, включая его записи инвентаризации и все внесенные комментарии.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Учтенные заказы инвентаризации**, а затем выберите связанную ссылку.
2. На странице **Учтенные заказы инвентаризации** выберите учтенный заказ инвентаризации, который требуется просмотреть, затем выберите действие **Просмотреть**.
3. Для просмотра списка соответствующих записей инвентаризации выберите действие **Записи**.

## <a name="handling-item-tracking-when-counting-inventory" />Обработка трассировки товаров при инвентаризации запасов

Трассировка товаров относится к серийным номерам или номера партий, назначенным товарам. При инвентаризации товара, который хранится в запасах как, например, 10 различных номеров партий, сотрудник должен быть в состоянии записать, какие и сколько единиц каждого номера партии находятся на складе. Дополнительные сведения о функции трассировки товаров см. в разделе [Работа с серийными номерами и номерами партий](inventory-how-work-item-tracking.md).

Флажок **Использовать трассировку товаров** в строках заказа инвентаризации автоматически устанавливается, если код трассировки товара настроен для товара, но можно также установить или снять его вручную.

### <a name="example---prepare-a-physical-inventory-recording-for-an-item-tracked-item" />Пример — подготовка записи инвентаризации для товара с трассировкой

Рассмотрим инвентаризацию для товара А, который хранится в запасах как десять различных серийных номеров.
1. В строке записи для товара установите флажок **Использовать трассировку товаров**.
2. Выберите поле **Серийный номер**, выберите первый серийный номер, который существует в запасах для товара, затем нажмите кнопку **ОК**.

    Скопируйте строку для первого товара, трассируемого по товарам, чтобы вставить дополнительные строки, соответствующие количеству серийных номеров, которые хранятся на складе.

3. Выберите действие **Функции**, затем действие **Копировать строку**.
4. На странице **Копировать строку записи инвентаризации** введите 9 в поле **Количество копий**, затем нажмите кнопку **ОК**.
5. В первой из скопированных строк выберите поле **Серийный номер** и выберите следующий серийный номер для товара.
6. Повторите шаг 5 для остальных восьми серийных номеров, следя, чтобы не выбрать одну строку дважды.
7. Выберите действие **Печать**, чтобы подготовить распечатку, которую сотрудники будут использовать для записи подсчитанных товаров и серийных номеров или номеров партий.

Обратите внимание, что отчет **Запись инвентаризации** содержит десять строк для товара А, по одной для каждого серийного номера.

### <a name="example---record-and-post-counted-lot-number-differences" />Пример. Запись и учет разницы инвентаризированных номеров партий

Товар с отслеживанием партии-хранится на складе с серией номеров "LOT".

**Ожидаемые запасы**:

|Номер партии|количество;|
|-|-|
|LOT1001|80|
|LOT1003|30|
|LOT1006|10|
|Итого|120|

**Зарегистрированные количества**:

|Номер партии|количество;|
|-|-|
|LOT1001|80|
|LOT0002|12|
|LOT1003|20|
|LOT1006|10|
|Итого|112|

**Количества к учету**:

|Номер партии|Ожидаемое количество|Зарегистрированное количество|Количество к учету|
|-|-|-|-|
|LOT1001|80|80|0|
|LOT1002|0|12|+12|
|LOT1003|30|20|-10|
|LOT1006|10|0|-10|
|Итого|120|112|–8|

На странице **Заказ инвентаризации** поле **Отриц. кол-во (баз.)** будет содержать *8*. Для рассматриваемой строки заказа страница **Список трассировки товара для инвентаризации** будет содержать положительные или отрицательные количества для отдельных номеров партий.

## <a name="inventory-documents" />Инвентарные документы

Следующие типы документов полезны при управлении складом:

* Используйте **Приходные накладные** для регистрации положительных корректировок товаров в зависимости от качества, количества и стоимости.
* Используйте **Расходные накладные** для списания недостающих или поврежденных товаров.

Вы можете распечатать эти документы на любом этапе, выпустить и снова открыть их, а также назначить общие значения, включая измерения, в заголовке. Если вы хотите перепечатать документы после их учета, вы можете сделать это на страницах **Учтенная приходная накладная** и **Учтенная расходная накладная**.

> [!NOTE]
> Прежде чем вы сможете использовать эти документы, вы должны указать номерную серию для создания их идентификаторов. Дополнительные сведения см. в следующем разделе.

### <a name="to-set-up-numbering-for-inventory-documents" />Чтобы настроить нумерацию инвентарных документов

Ниже приводится процедура настройки нумерации для инвентаризационных документов.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Настройка запасов**, а затем выберите связанную ссылку.
2. На экспресс-вкладке **Нумерация** укажите в следующих полях серии номеров документов.

   * **Номера приходных накладных**  
   * **Номера учтенных приходных накладных**  
   * **Номера расходных накладных**  
   * **Номера учтенных расходных накладных**  

### <a name="to-create-and-post-an-inventory-document" />Чтобы создать и учесть инвентарный документ

В следующей процедуре показан порядок создания, печати и учета приходной накладной. Действия для расходных накладных аналогичны.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Приходные накладные**, а затем выберите связанную ссылку.  
2. В заголовке страницы **Приходная накладная** выберите расположение в поле **Код местонахождения**, затем заполните оставшиеся поля по мере необходимости.
3. На экспресс-вкладке **Строки** в поле **Товар** выберите товар в запасах. В поле **Кол-во** укажите количество товаров для добавления. 
4. Для печати отчета **Приходная накладная** со страницы **Приходная накладная** выберите действие **Печать**.

Следующие функции доступны на странице **Приходная накладная**:

* Выберите действие **Выпустить** или **Открыть повторно** для задания состояния для следующего этапа обработки  
* Выберите действие **Учесть**, чтобы учесть приходную накладную, или выберите **Учесть и распечатать**, чтобы учесть приход и распечатать тестовый отчет  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## <a name="printing-inventory-documents" />Печать инвентарных документов

Вы можете указать отчеты, которые необходимо распечатать на разных этапах, выбрав один из следующих вариантов в поле **Использование** страницы **Выбор отчета — запасы**:

* Приходная накладная
* Расходная накладная
* Учтенная приходная накладная
* Учтенная расходная накладная

> [!NOTE]
> Доступные отчеты могут отличаться в зависимости от локализации вашей страны или региона. Базовое приложение не содержит никаких макетов.

## <a name="see-related-microsoft-trainingtrainingmodulesadjust-inventory" />См. соответствующее [обучение Microsoft](/training/modules/adjust-inventory/)

## <a name="see-also" />См. также

[Подсчет, корректировка и повторная классификация запасов с помощью журналов](inventory-how-count-adjust-reclassify.md)  
[Работа с серийными номерами и номерами партий](inventory-how-work-item-tracking.md)  
[Запасы](inventory-manage-inventory.md)  
[Обзор управления складом](design-details-warehouse-management.md)  
[Продажи](sales-manage-sales.md)  
[Покупки](purchasing-manage-purchasing.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
