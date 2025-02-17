---
title: 'Сведения о проектировании: балансировка поставки и спроса'
description: 'В этой статье описывается, как упорядочить цели, уравновешивая спрос и предложение.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 12/15/2022
ms.custom: bap-template
---
# <a name="design-details-balancing-supply-and-demand" />Сведения о проектировании: балансировка поставки и спроса

Чтобы понять, как работает система планирования, важно понять ее приоритетные цели:  

* Любой спрос будет удовлетворен достаточной поставкой.  
* Любая поставка служит цели.  

В целом, эти цели достигаются путем балансировки поставки со спросом.  

## <a name="supply-and-demand" />Поставки и спрос

Термин *поставки* относится к любому виду положительного или входящего количества, например:

* Складируемый
* Покупки
* Сборка
* Зона производства
* Входящие перемещения
* Возвраты продаж  

Термин *спрос* относится к любому виду общего спроса, например:

* Товар для заказ на продажу
* Компонент для производственного заказа

[!INCLUDE [prod_short](includes/prod_short.md)] также позволяет использовать более технические типы спроса, такие как отрицательные остатки и возврат покупки.

Для сортировки поставки и спроса система планирования организует их в два временных ряда, которые называются профилями склада. В одном профиле содержатся события спроса, в другом — соответствующие события поставок. Каждое событие поставки представляет одну сущность в заказе, например:

* Строка заказа на продажу
* Операция книги товаров
* Строка производственного заказа

При загрузке профилей запасов наборы спроса и предложения уравновешиваются, чтобы получить в результате план поставки, соответствующий перечисленным целям.

Уровни запасов и параметры планирования являются другими типами поставки и спроса. Эти типы проходят комплексную балансировку для пополнения товаров склада. Подробнее см. в разделе [Сведения о проектировании: обработка политик дозаказа](design-details-handling-reordering-policies.md).

## <a name="the-concept-of-balancing-in-brief" />Краткие сведения о балансировке

Спрос исходит от ваших клиентов. Поставка — это то, что вы создать или удалить для обеспечения баланса. Система планирования начинает с спроса, а затем в обратном направлении выполняет отслеживание до предложения.  

Профили инвентаризации содержат информации о спросе и предложении, количествах и времени. Эти профили составляют две стороны шкалы уравновешивания.  

Задача механизма планирования — уравновешивать поставки и спрос товара, чтобы убедиться, что предложение соответствует спросу, как определено параметрами и правилами планирования.  

:::image type="content" source="media/nav_app_supply_planning_2_balancing.png" alt-text="Обзор баланса поставки и спроса.":::

## <a name="process-orders-before-the-planning-start-date" />Обработка заказов до даты начала планирования

Чтобы избежать появления в плане поставки необоснованных предложений, система планирования не будет ничего планировать в период до даты начала планирования. Следующее правило применяется к такому периоду:

* Весь поставки и спрос до даты начала периода планирования считаются частью запасов или будут считаться отгруженными.  

За некоторыми исключениями система планирования не будет предлагать какие-либо изменения в заказах на поставку за период или создавать связи трассировки заказа за этот период. В этом правиле следующие исключения:  

* Прогнозируемый доступный запас, включая сумму поставки и спроса в периоде, меньше нуля.  
* Для заказов, записываемых задним числом, требуются серийные номера или номера партий.  
* Набор поставки и спроса связан требованиями политики "заказ-в-заказ". 

Если исходные доступные запасы ниже нуля, система планирования предложит экстренный заказ на поставку на день, предшествующий периоду планирования для обеспечения наличия отсутствующего количества. Следовательно, прогнозируемые и доступные запасы всегда будут равны хотя бы нулю, когда начинается планирование будущего периода. Строка планирования для этого заказа на поставку отобразит предупреждающий значок аварийной ситуации с возможностью просмотра дополнительных сведений.

### <a name="serial-and-lot-numbers-and-order-to-order-links-are-exempt-from-the-previous-period" />Серийные номера или номера партий и связи "заказ-в-заказ" исключены из предыдущего периода

Если требуются серийные номера или номера партий или связь "заказ-в-заказ" существуют, система планирования игнорирует правило о предыдущем периоде. Он будет включать количества, датированные задним числом, начиная с начальной даты, и может предлагать корректирующие действия, если поставки и спрос не синхронизированы. Эти наборы спроса и предложения должны совпадать, чтобы гарантировать выполнение определенного спроса.

## <a name="load-inventory-profiles" />Загрузка профилей запасов

Для сортировки поставки и спроса система планирования организует их в два временных ряда, которые называются профилями склада.  

Поставки и спрос с датами оплаты в дату начала планирования или после загружаются в каждый профиль запасов. При загрузке типы поставки и спроса сортируются в соответствии с общими приоритетами, такими как:

* Срок
* Коды низкого уровня
* Склад
* Вариант

К различным типам применяются приоритеты для удовлетворения самый важный спрос в первую очередь. Подробнее читайте в разделе [Определение приоритета заказов](design-details-balancing-demand-and-supply.md#prioritize-orders) .  

Спрос может быть и отрицательным. Относитесь к отрицательному спросу как к поставке. Однако, в отличие от типичного предложения, отрицательный спрос считается фиксированной поставкой. Система планирования может принимать это во внимание, но изменения предложены не будут.  

В целом, система планирования может изменить все заказы на поставку после даты начала планирования, чтобы удовлетворить спрос. Однако после разноски количества из заказа на поставку, его больше невозможно изменить с помощью системы планирования. Следующие заказы не могут быть перепланированы:  

* Запущенные производственные заказы, в которых учтено потребление или выход.  
* Заказы на сборку, в которых учтено потребление или выход.  
* Заказы на перемещение с учтенной расходной накладной.  
* Заказы на покупку, в которых учтена приходная накладная.  

Помимо загрузки типов поставки и спроса некоторые типы загружаются с учетом специальных правил и зависимостей. В следующих разделах этой статьи описываются эти правила и зависимости.  

### <a name="item-dimensions-are-separated" />Измерения товара разделяются

План поставки необходимо вычислить для каждой комбинации измерений товаров, например варианта или склада. Следует рассчитать только комбинации, которые включают спрос и/или поставку.  

Система планирования ищет комбинации в профиле запасов. Если найдена новая комбинация, система создает запись внутреннего контроля, содержащую сведения об этой комбинации. Система планирования вставляет единицу хранения в качестве записи контроля или наружного цикла. В результате задаются параметры планирования в соответствии с комбинацией варианта и склада, и система может перейти во внутренний цикл. 

> [!NOTE]  
> Нет необходимости ввода записи единицы хранения при вводе спроса и(или) поставки для определенной комбинации варианта и склада. Следовательно, если единица хранения для данной комбинации отсутствует, [!INCLUDE [prod_short](includes/prod_short.md)] создает временную запись единицы хранения на основе данных карточки товаров. Если для поля **Склад обязателен** задано значение "Да" на странице **Настройка модуля "Запасы"**, следует создать единицу хранения или для поля **Компоненты по складам** следует задать значение "Да". Подробнее см. в разделе [Планирование со складами и без складов](production-planning-with-without-locations.md).  

### <a name="serial-and-lot-numbers-are-loaded-by-specification-level" />Серийные номера и номера партий загружаются по уровням спецификации

Серийные номера и номера партий загружаются в профили запасов вместе с поставки и спрос, которым они назначены.  

Атрибуты поставки и спроса организованы по приоритету заказа и по уровню спецификации. Поскольку совпадения серийного номера и номера партии отражают уровень спецификации, более конкретный запрос будет соответствовать менее конкретному запросу. Например, конкретным спросом может быть номер партии, указанный для строки продажи. Менее конкретным спросом может быть продажа с любого номера партии.

> [!NOTE]  
> Единственными специальными правилами определения приоритетности для поставки и спроса с серийными номерами и номерами партий является уровень спецификации, определяемый их комбинациями, а также настройки трассировки товаров.  

Во время балансировки система планирования рассматривает поставку с серийным номером и номером партии как негибкую. Система не будет увеличивать или перепланировать такие заказы на поставку. Единственным исключением из этого правила являются случаи, когда они используются в отношении "заказ-в-заказ". См. раздел ["Связи "заказ-в-заказ" никогда не нарушаются"](#order-to-order-links-are-never-broken). Это исключение защищает поставку от получения нескольких (возможно, противоречивых) указаний, когда поставка содержит варьирующиеся атрибуты. Например, различные атрибуты могут иметь место, когда поставка имеет набор разных серийных номеров.  

Другая причина, по которой поставки с серийным номером и номером партии являются негибкими, заключается в том, что серийный номер и номер партии часто присваиваются в конце процесса. Если в этот момент будут предложены изменения, это может сбить с толку.  

Балансировка серийного номера и номера партии не соблюдает правило ничего не планировать до даты начала планирования. Если поставки и спрос не синхронизированы, система планирования предложит изменения или новые заказы независимо от даты начала планирования.  

### <a name="order-to-order-links-are-never-broken" />Связи "заказ-в-заказ" никогда не нарушаются

При планировании товара "заказ к заказу" связанное поставку можно использовать только для спроса, для которого оно изначально предназначалось. Связанный спрос не должен охватываться никакими другими произвольными поставками, даже если эта поставка доступна по времени и количеству. Например, заказ на сборку, связанный с заказом на продажу в сценарии сборки на заказ, невозможно использовать для удовлетворения другого спроса.  

Поставки и спрос "заказ-в-заказ" должны быть сбалансированы точно. Система планирования обеспечивает поставку невзирая на параметры определения размера заказов, модификаторы и количества на складе (кроме количеств, относящихся к связанным заказам). По этой же причине система предложит уменьшить излишки при уменьшении связанного спроса.  

Эта балансировка влияет и на время. Ограниченный горизонт, предоставленный горизонтом планирования, не учитывается; поставка перепланируется, если время спроса изменилось. Однако буферный период будет соблюден и не позволит запланировать поставки заказ-в-заказ на более позднюю дату, за исключением внутренних поставок многоуровневого производственного заказа (проектный заказ).  

> [!NOTE]  
> Серийные номера и номера партий также можно указать в спросе "заказ-в-заказ". В этом случае поставка не считается негибкой, что обычно для серийных номеров и номеров партий. В этом случае система увеличит или уменьшит количество в соответствии с изменениями в спросе. Если один спрос включает различные серийные номера и номера партий, например несколько номеров партий, будет предложен один заказ на поставку для каждой партии.  

> [!NOTE]  
> Прогнозы не должны приводить к созданию заказов на поставку, объединенных связью "заказ-в-заказ". Если используется прогноз, он должен использоваться только как средство создания зависимого спроса в производственной среде.

### <a name="component-need-is-loaded-according-to-production-order-changes" />Требуемый компонент отправляется в соответствии с изменениями в производственном заказе

При обработке производственных заказов система планирования должна осуществлять мониторинг необходимых компонентов перед загрузкой в профиль спроса. Строки компонентов, полученные в результате изменений производственного заказа, заменят строки исходного заказа. Это изменение гарантирует, что система планирования не дублирует строки планирования для потребности в компоненте.  

### <a name="consume-safety-stock" />Потребление страхового запаса

Кол-во страхового запаса является спросом, который загружается в профиль запасов на дату начала планирования.  

Страховой запас — это количество запасов, заданное отдельно для устранения неопределенностей в спросе во время подготовки пополнения. Однако его можно потреблять, чтобы удовлетворить спрос. В этом случае система планирования обеспечит быструю замену страхового запаса. Система предлагает заказ на поставку для пополнения количества страхового запаса на дату его использования. В строке планирования будет отображен значок предупреждения об исключении, объясняющего, что страховой запас был частично или полностью потреблен в результате исключительного заказа на отсутствующее количество.  

### <a name="forecast-demand-is-reduced-by-sales-orders" />Прогнозируемый спрос снижается заказами на продажу

Прогноз спроса выражает предполагаемый спрос в будущем. Несмотря на то что вводится фактический спрос как заказы на продажу произведенных товаров, это значение поглощает спрогнозированное.

Сам прогноз не уменьшается из-за заказов на продажу. Однако прогнозируемые количества, используемые при расчете планирования, уменьшаются (с помощью количеств заказа на продажу) перед тем, как остаток вводится в профиль спроса. Для продаж в течение периода планирование включает в себя как открытые заказы на продажу, так и операции книги товаров по отгруженным продажам. Исключением из этого правила являются случаи, когда они исходят из общего заказа.  

Необходимо определить допустимый период прогноза. Дата на прогнозном количестве определяет начало периода, а дата на следующем прогнозе определяет окончание периода.  

Прогноз для периодов до периода планирования не используется независимо от того был ли он израсходован. Первая прогнозируемая цифра процентов — это либо дата, совпадающая с датой начала планирования, или ближайшая предшествующая ей дата.  

Прогноз может быть для разных видов спроса:

* Независимый спрос, например заказы на продажу
* Зависимый спрос, например компоненты производственного заказа.

Товар может иметь оба типа прогноза. Во время планирования потребление происходит отдельно, сначала для независимого спроса, а затем для зависимого спроса.  

### <a name="blanket-order-demand-is-reduced-by-sales-orders" />Спрос общего заказа снижается заказами на продажу

Прогнозирование дополняется общими заказами, чтобы определить будущий спрос для определенного клиента. Как и в случае (неуказанного) прогноза, фактические продажи должны потреблять ожидаемый спрос, а остаток должен вводиться в профиль запасов спроса. Потребление не уменьшает количество общего заказа.

Расчет планирования включает открытые заказы на продажу, связанные с конкретными строками общего заказа, но не включает какой-либо допустимый период времени. Также не включаются учтенные заказы, поскольку в ходе выполнения процедур учета недопоставленное количество общего заказа уже уменьшено.

## <a name="prioritize-orders" />Определение приоритета заказов

В пределах данной единицы хранения запрошенная или доступная дата имеет наивысший приоритет. Сегодняшний спрос должен быть удовлетворен до спроса на следующей неделе. Но, в дополнение к этому общему приоритету, система планирования будет делать следующие предложения в соответствии с приоритетами заказа:

* Какой тип спроса вы должны выполнить в первую очередь.
* Какой источник поставки следует применить до применения других источников поставки.  

Загруженный поставки и спрос влияют на профиль для прогнозируемых запасов в соответствии с приоритетами.  

### <a name="priorities-on-the-demand-side" />Приоритеты на стороне спроса

1. Уже отгружено: операция книги товаров  
2. Возврат покупки  
3. Заказ на продажу  
4. Сервисный заказ  
5. Требуемый производственный компонент  
6. Строка заказа на сборку  
7. Заказ на исходящее перемещение  
8. Общий заказ (еще не использованный в связанных заказах на продажу)  
9. Прогноз (еще не использованный в других заказах на продажу)  

> [!NOTE]  
> Возвраты покупок обычно не включаются в планирование поставок; они всегда должны резервироваться из партии, которая будет возвращена. Если возвраты покупок не зарезервированы, они играют роль в наличии и имеют высокий приоритет, чтобы система планирования не предлагала заказ на поставку лишь для того, чтобы обслужить возврат покупки.  

### <a name="priorities-on-the-supply-side" />Приоритеты на стороне поставки

1. Уже существует на складе: операция книги товаров ("Гибкость планирования" = "Нет")  
2. Возврат продажи ("Гибкость планирования" = "Нет")  
3. Заказ на входящее перемещение  
4. Производственный заказ  
5. Заказ на сборку  
6. Заказ на покупку  

### <a name="priority-related-to-the-state-of-supply-and-demand" />Приоритет, связанный с состоянием поставки и спроса

Помимо приоритетов от типа поставки и спроса, есть и другие вещи, влияющие на гибкость планирования. Например, складские операции и статус следующих заказов:

* Продажи
* Покупка
* Перемещение
* Сборка
* Зона производства

Статус этих заказов оказывает следующее воздействие: 

1. Частично скорректировано ("Гибкость планирования" = "Нет")  
2. Уже обрабатывается на складе ("Гибкость планирования" = "Нет")  
3. Выпущено — все типы заказов ("Гибкость планирования" = "Неограниченно")  
4. Утвержденный производственный заказ ("Гибкость планирования" = "Неограниченно")  
5. Запланировано/открыто — все типы заказов ("Гибкость планирования" = "Неограниченно")

## <a name="balancing-supply-with-demand" />Балансировка поставки и спроса

Система планирования уравновешивает поставки и спрос, предлагая действия по пересмотру несбалансированных заказов на поставку. Это уравновешивание происходит для каждой комбинации варианта и склада.  

Представьте, что каждый профиль запасов содержит две строки:

* Строка событий спроса, отсортированных по дате и приоритету
* Соответствующая строка событий поставки

Каждое событие ссылается на тип источника и идентификации. Правила уравновешивания товаров достаточно просты. Соответствие поставки и спроса может возникнуть на любом этапе процесса следующим образом:  

1. Спрос и поставка не существуют для товара => планирование завершено (или не должно начинаться).  
2. Спрос существует, но нет поставки => необходимо предложить поставку.  
3. Поставка существует, но на нее нет спроса => поставка должна быть отменена.  
4. Поставки и спрос существуют => следует задать вопросы и получить ответы до того, как [!INCLUDE [prod_short](includes/prod_short.md)] сможет обеспечить удовлетворение спроса поставкой.

    Если время поставки неподходящее, возможно, поставку можно перепланировать следующим образом:  

    1. Если поставка размещается раньше спроса, возможно, поставку можно запланировать на более позднюю дату, чтобы запасы были как можно меньше.  
    2. Если поставка размещается после спроса, возможно, поставку можно запланировать на более раннюю дату. В противном случае система предложит новую поставку.  
    3. Если поставка удовлетворяет спрос на определенную дату, система планирования может провести анализ того, может ли количество поставки удовлетворить спрос.  

    Если расчет времени выполнен, можно рассчитать количество для поставки следующим образом:  

    1. Если количество поставки меньше спроса, количество поставки можно увеличить (или нет, если имеются ограничения в соответствии с политикой максимального количества).  
    2. Если количество поставки больше спроса, количество поставки можно уменьшить (или нет, если имеются ограничения в соответствии с политикой минимального количества).  

    На данном этапе возникает одна из двух ситуаций:  

    1. Текущий спрос можно удовлетворить, в таком случае он закрывается и начинается планирование для следующего спроса.  
    2. Поставка достигла максимума, некоторая часть спроса не покрыта. В этом случае система планирования может закрыть текущую поставку и перейти к следующей поставке.  

 Процедура начинается снова со следующего спроса и текущей поставки, и наоборот. Текущее предложение может быть в состоянии покрыть и следующий спрос, либо текущий спрос не покрыт полностью.  

### <a name="rules-for-actions-for-supply-events" />Правила для действий для событий поставки

Для нисходящих расчетов, в которых поставка должна соответствовать спросу, спрос принимается как данность. Это вне контроля системы планирования. Однако система планирования может управлять стороной поставки и будет делать следующие предложения:

* Создать новые заказы на поставку
* Перепланировать существующие заказы или изменить их количество
* Отменить заказы на поставку, которые больше не нужны  

Чтобы исключить существующий заказ на поставку из предложений по планированию, можно задать отсутствие гибкости планирования ("Гибкость планирования" = "Нет"). Затем излишки поставок по этому заказу будут использоваться для покрытия спроса, однако никакое действие предложено не будет. 

В целом, вся поставка имеет гибкость планирования, которая ограничена условиями каждого из предложенных действий.  

* **Перепланировать на более позднюю дату**. Дату существующего заказа на поставку можно запланировать на более позднюю дату для соблюдения даты выполнения спроса за исключением следующих ситуаций:

  * Она представляет запасы (всегда на день ноль).  
  * Она имеет связь "заказ-в-заказ" с другим спросом.  
  * Это вне окна для перепланирования в горизонте планирования.
  * Можно использовать более близкую поставку.  
  * С другой стороны, пользователь может решить не выполнять перепланирование по следующим причинам:
  * Заказ на поставку связан с другим спросом в предыдущую дату.  
  * Требуемое планирование настолько незначительно, что им можно пренебречь.  

* **Перепланировать на более раннюю дату**: дату существующего заказа на поставку можно запланировать на более раннюю дату, за исключением следующих ситуаций:

  * Она связана непосредственно с некоторым другим спросом.  
  * Это вне окна для перепланирования, определенного в горизонте планирования.

> [!NOTE]  
> При планировании товара с использованием точки повторного заказа всегда можно перепланировать заказ на поставку. Это часто происходит для заранее планируемых заказов на поставку, инициируемых точкой повторного заказа.

* **Увеличить количество**. Количества существующего заказа на поставку можно увеличить для удовлетворения спроса, если заказ на поставку не связан напрямую со спросом с помощью связи "заказ-в-заказ".  

> [!NOTE]  
> Также заказ на поставку можно увеличить, увеличение может быть ограничен определенным максимальным количеством заказа.  

* **Уменьшение количества**. Существующий заказ на поставку с излишком по сравнению с существующим спросом можно уменьшить для удовлетворения спроса.  

> [!NOTE]  
> Хотя количество можно уменьшить, все равно может наблюдаться некоторый излишек по сравнению со спросом из-за определенного минимального количества заказа или множителя заказа. 

* **Отмена**: в качестве особого случая действия уменьшения количества заказ на поставку можно отменить, если его количество уменьшено до нуля. 
* **Новый**: если заказ на поставку еще не существует или существующий заказ на поставку невозможно изменить для покрытия необходимого количества на дату удовлетворения спроса, предлагается новый заказ на поставку.  

### <a name="determine-the-supply-quantity" />Определить количество поставки

Вы определяете параметры планирования, которые управляют предлагаемым количеством каждого заказа на поставку.  

Если система планирования вычисляет количество нового заказа на поставку или изменение количества существующего заказа, предложенное количество может отличаться от фактического спроса.  

Если выбран максимальный запас или фиксированные количества заказа, предлагаемое количество может быть увеличено для соответствия фиксированному количеству или максимальному запасу. Если политика дозаказа использует точку дозаказа, количество может быть увеличено по меньшей мере для соответствия точке дозаказа. 

Предложенное количество может быть изменено в этой последовательности.  

1. Уменьшено до максимального количества заказа.  
2. До минимального количества заказа.  
3. До ближайшего множителя заказа.

### <a name="order-tracking-links-during-planning" />Связи трассировки заказов во время планирования

Что касается трассировки заказов во время планирования, система планирования изменяет порядок связей трассировки заказа для комбинаций товаров, вариантов и складов. Система переставляет связи трассировки по следующим причинам:

* Чтобы проверить свои предложения по покрытию всего спроса и убедиться, что все заказы на поставку необходимы.  
* Связи трассировки заказов необходимо регулярно заново балансировать.  

Со временем связи трассировки заказов становятся несбалансированными. Связи становятся несбалансированными, поскольку вся сеть трассировки заказов не перестраивается, пока события спроса или поставок не будут закрыты.

Перед балансировкой поставки по спросу система планирования удаляет все связи трассировки заказа. Во время процесса балансировки, когда событие поставки и спроса закрывается, создаются новые связи трассировки заказов между поставки и спросом.  

> [!NOTE]  
> Даже если товар не настроен для динамической трассировки заказов, система планирования создаст сбалансированные связи трассировки заказа.

## <a name="close-balanced-supply-and-demand" />Закрыть сбалансированные поставки и спрос

Балансирование поставки имеет три возможных результата:

* Требуемое количество и дата событий спроса удовлетворены, их планирование можно закрывать. Событие предложения остается открытым и может покрыть следующий спрос. Сохранение события поставки открытым позволяет начать процедуру балансировки с текущего события поставки и следующего спроса.  
* Заказ на поставку невозможно изменить, чтобы покрыть весь спрос. Событие спроса все еще открыто, некоторое неохваченное количество которого может быть покрыто следующим событием предложения. Таким образом, текущее событие поставки закрыто, и действие балансировки можно начинать с текущего события спроса и следующего события поставки.  
* Весь спрос удовлетворен и следующего спроса нет (либо спрос отсутствовал вовсе). Излишняя поставка может быть уменьшена (или отменена), а затем закрыта. Любые другие события поставки также должны быть отменены.  

Наконец, система планирования создаст связь трассировки заказа между поставкой и спросом.  

### <a name="create-the-planning-line-suggested-action" />Создать строку планирования (предлагаемое действие)

Если предлагается действие **Создать**, **Изменить кол-во**, **Перепланировать**, **Перепланировать и изменить кол-во** или **Отменить** для изменения заказа на поставку, система планирования создает строку планирования в журнале планирования. Для отслеживания заказов строка планирования создается не только при закрытии события поставки, но и при закрытии события спроса. Это справедливо даже при том, что событие поставки все еще открыто и может быть изменено при обработке следующего события спроса. При создании впервые строка планирования снова может быть изменена.

Для снижения нагрузки на базу данных при обработке производственных заказов строку планирования можно вести на трех уровнях:

* Создайте только строку планирования с текущим сроком оплаты и количеством, но без маршрута и компонентов.  
* Включите маршрут: запланированный маршрут, включающий расчет с дат и времени начала и окончания. Включение маршрута требует доступа к базе данных. Определение конечных дат и сроков оплаты может потребовать вычисления маршрута, даже если событие поставки не было закрыто. Например, если вы делаете опережающее планирование.  
* Включите развертывание спецификации: это может произойти прямо перед закрытием события.

## <a name="see-also" />См. также

[Сведения о проектировании: основные понятия системы планирования](design-details-central-concepts-of-the-planning-system.md)  
[Сведения о проектировании: обработка политик дозаказа](design-details-handling-reordering-policies.md)  
[Сведения о проектировании: планирование поставок](design-details-supply-planning.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
