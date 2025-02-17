---
title: 'Сведения о проектировании: обработка политик дозаказа'
description: 'В этой статье представлен обзор политик повторного заказа, которые можно использовать при планировании поставок.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: conceptual
ms.date: 02/24/2023
ms.custom: bap-template
---
# <a name="design-details-handling-reordering-policies" />Сведения о проектировании: обработка политик дозаказа

Чтобы включить товар в планирование поставок, необходимо указать политику повторного заказа для него на странице **Карточка товара**. Доступны следующих политики повторного заказа:  

* Фикс. кол-во повтора заказа  
* Максимальное кол-во  
* Заказ  
* Партия на партию  

Политики **Фикс. кол-во повтора заказа** и **Максимальное кол-во** относятся к планированию запасов. Эти политики сосуществуют с поэтапной балансировкой поставок и трассировкой заказов.  

## <a name="the-role-of-the-reorder-point" />Роль точки повтора заказа

Точка дозаказа представляет спрос во время подготовки. Когда прогнозируется, что запасы опустятся ниже уровня, определенного точкой повторного заказа, время заказывать еще. Запасы будет постепенно уменьшаться, пока не прибудет пополнение. Он может достичь нуля или уровня страхового запаса. Система планирования предложит заранее планируемый заказ на поставку в момент перехода запасов ниже точки повтора заказа.  

Уровни запасов могут значительно измениться в горизонте планирования. Поэтому система планирования постоянно отслеживает доступные запасы.

## <a name="monitoring-the-projected-inventory-level-and-the-reorder-point" />Отслеживание уровня прогнозируемых запасов и точки повтора заказа

Запасы — это тип поставки, но для планирования запасов система планирования разделяет два уровня запасов:  

* Прогнозируемые запасы  
* Прогнозируемые доступные запасы  

### <a name="projected-inventory" />Прогнозируемые запасы

В начале процесса планирования прогнозируемые запасы представляют собой общее количество запасов. Общее количество включает учтенные и неучтенные поставки и спрос в прошлом. Это количество становится прогнозируемым уровнем запасов, который поддерживается валовыми количествами из будущего поставки и спрос. Будущие поставки и спрос вводятся на временной шкале независимо от того, резервируются они или распределяются другими способами.  

Прогнозируемые запасы используются системой планирования для мониторинга точки повтора запаса и определения количества повтора запаса при использовании политики повтора заказа **Максимальное кол-во**.  

### <a name="projected-available-inventory" />Прогнозируемые доступные запасы

Прогнозируемые доступные запасы являются запасом, которая на данный момент доступна для удовлетворения спроса. Прогнозируемые доступные запасы используются системой планирования при мониторинге уровня страхового запаса. Страховой запас всегда должен быть доступен для неожиданного спроса.  

### <a name="time-buckets" />Горизонты планирования

Прогнозируемый запас важен для определения момента достижения или пересечения точки повтора заказа, а также для расчета правильного количества заказа при использовании политики повтора заказа **Максимальное кол-во**.  

Прогнозируемый уровень запасов рассчитывается в начале периода учета. Это общий уровень, на котором не учитываются резервирования и другие распределения. Для мониторинга этого уровня запасов в последовательности планирования система планирования отслеживает совокупные изменения за период времени. Этот период называется *горизонт планирования*. Чтобы узнать больше о горизонт планирования, перейдите в раздел [Горизонт планирования](#time-buckets). Система планирования гарантирует, что горизонт планирования составляет не менее одного дня. Один день — это минимальная единица времени для событий спроса или предложения.  

### <a name="determining-the-projected-inventory-level" />Определение уровня прогнозируемых запасов

Следующая последовательность описывает определение прогнозируемого уровня запасов системой планирования:  

* Когда событие поставки, например заказ на покупку, полностью спланировано, увеличиваются ожидаемые запасы в дату оплаты события.  
* Если событие спроса полностью удовлетворено, прогнозируемый расход склада не будет осуществляться сразу же. Вместо этого разносится напоминание об уменьшении, которое является внутренней записью, содержащей дату и количество добавления в прогнозируемые запасы.  
* Когда более позднее событие поставки планируется и добавляется на временную шкалу, система исследует размещенные напоминания об уменьшении одно за другим до запланированной даты поставки. Во время данного процесса уровень точки дозаказа внутреннего напоминания об увеличении может быть достигнут или пройден.  
* Если введен новый заказ на поставку, она проверяет, был ли он введен до текущей поставки. В этом случае новая поставка становится текущей поставкой, и процедура балансировки начинается снова.  

На следующем изображении показан этот принцип.  

![Определение уровня прогнозируемых запасов.](media/nav_app_supply_planning_2_projected_inventory.png "Определение уровня прогнозируемых запасов")  

1. Поставка **Sa** на 4 штуки (фиксированная) закрывает спрос **Da** на -3 штуки.  
2. CloseDemand: создается напоминание об уменьшении на -3 (не показано).  
3. Поставка **Sa** закрыта с излишком 1 (спрос больше не существует).  

     В результате прогнозируемый уровень запасов увеличивается до +4, а прогнозируемые **доступные** запасы равны -1.  

4. Следующая поставка **Sb** на 2 штуки (другой заказ) уже помещена на временную шкалу.  
5. Система проверяет, имеется ли напоминание об уменьшении, предшествующее **Sb** (в данном примере нет, поэтому никакие действия не предпринимаются).  
6. Система закрывает поставку **Sb** (спрос больше не существует) либо A: путем снижения количества до значения 0 (отмена), либо Б: оставляя ее как есть.  

     Прогнозируемый уровень запасов растет (A: +0 => +4 или Б: +2 = +6).  

7. Система планирования делает окончательную проверку. Есть ли напоминание об уменьшении? Да, имеется один в дату **Da**.  
8. Система планирования добавляет напоминание об уменьшении, равном -3, к прогнозируемому уровню запасов одним из двух способов: A: +4 -3 = 1 или Б: +6 -3 = +3.  
9. В случае А система создает заранее планируемый заказ, начиная с даты **Da**. В случае Б достигается точка дозаказа и создается новый заказ.

## <a name="the-role-of-the-time-bucket" />Роль горизонта планирования

Цель горизонта планирования — сбор событий спроса на странице времени с целью составления совместного заказа на поставку.  

Для политик дозаказа, в которых используется точка дозаказа, можно определить горизонт планирования. Горизонты планирования помогают обеспечить накопление спроса за один и тот же период времени. Затем система проверяет влияние на прогнозируемый запас и пройдена ли точка повторного заказа.

Если точка дозаказа пройдена, система планирует заранее заказ на поставку на конец горизонте планирования. Горизонты планирования начинаются в начальную дату планирования.  

Концепция горизонта планирования отражает осуществляемый вручную процесс проверки уровня запасов на регулярной основе, а не для каждой транзакции. Вам требуется определить периодичность (горизонт планирования). Например, можно объединяет все потребности в товарах для одного поставщика для размещения еженедельного заказа.  

![Пример горизонта планирования.](media/nav_app_supply_planning_2_reorder_cycle.png "Пример горизонта планирования")  

Горизонты планирования часто используется для того, чтобы избежать каскадного эффекта. Например, создается сбалансированная строка спроса и поставки, в которой отменяется преждевременный спрос. Результатом будет перепланирование всех заказов на поставку (кроме последнего).

## <a name="stay-below-the-overflow-level" />Оставайтесь ниже уровня допустимого избытка

При использовании политик **Максимальное кол-во** и **Фикс. кол-во повтора заказа** система планирования концентрируется на прогнозируемых запасов исключительно в данном горизонте планирования. Это может указывать на дополнительную поставку, когда отрицательный спрос или положительные изменения поставки происходят за пределами горизонта планирования. Для дополнительной поставки система планирования рассчитывает количество, на которое следует уменьшить поставку. Это количество называется "допустимый избыток". Избыток передается как строка планирования с действием **Изменить кол-во (уменьшить)** или **Отмена** и следующим предупреждением:  

* Внимание! Прогнозируемые запасы [xx] больше, чем допустимый избыток [xx] на срок выполнения [xx].*  

![Допустимый избыток запасов.](media/supplyplanning_2_overflow1_new.png "Допустимый избыток запасов")  

### <a name="calculating-the-overflow-level" />Расчет допустимого избытка

Допустимый избыток вычисляется разными способами в зависимости от политики повторного заказа.  

#### <a name="maximum-qty" />Максимальное кол-во

Допустимый избыток = максимальный запас  

> [!NOTE]  
> Если вы используете минимальный объем заказа, он добавляется следующим образом:
>
> допустимый избыток = максимальный запас + минимальный объем заказа.  

#### <a name="fixed-reorder-qty" />Фикс. кол-во повтора заказа

допустимый избыток = кол-во дозаказа + точка дозаказа  

> [!NOTE]  
> Если минимальный объем заказа превышает точку повторного заказа, он заменяется следующим образом:
>
> допустимый избыток = кол-во дозаказа + минимальное количество заказа  

#### <a name="order-multiple" />«Заказать несколько»;

Если существует множитель заказа, он корректирует допустимый избыток для политик дозаказа "Максимальное кол-во" и "Фикс. кол-во дозаказа".  

### <a name="creating-the-planning-line-with-an-overflow-warning" />Создание строки планирования с предупреждением о переполнении

Строка планирования создается, когда из-за существующей поставки прогнозируемые запасы выше допустимого избытка по окончании горизонта планирования. Чтобы предупредить о возможных избытках поставки, строка планирования содержит предупреждение, поле **Принять указание** не выбрано, а указание имеет значение **Отмена** или **Изменить кол-во**.  

#### <a name="calculating-the-planning-line-quantity" />Расчет количества строки планирования

Количество в строке планирования вычисляется следующим образом:

количество строки планирования = текущее количество поставки - (ожидаемые запасы — допустимый избыток)  

> [!NOTE]  
> Как и во всех строках предупреждений любое максимальное и минимальное количество заказа и множитель заказа будут игнорироваться.  

#### <a name="defining-the-action-message-type" />Определение типа сообщения о действии

* Если количество в строке планирования выше 0, отображается сообщение о действии **Изменить кол-во**.  
* Если количество в строке планирования ниже или равно 0, отображается сообщение о действии "**Отмена**".  

#### <a name="composing-the-warning-message" />Создание предупреждающего сообщения

В случае избытка на странице **Нетрассируемые элементы планирования** отображается предупреждающее сообщение со следующими сведениями:  

* Прогнозируемый уровень запасов, инициировавший предупреждение  
* Вычисленный допустимый избыток  
* Дата оплаты события предложения  

Пример. Прогнозируемые запасы 120 больше, чем допустимый избыток 60 в 01-28-23  

### <a name="example-scenario" />Пример сценария

В этом сценарии клиент меняет количество заказа на продажу с 70 на 40 штук в период между двумя процессами планирования. Функция переполнения снижает покупку, которая была предложена для первоначального количества продаж.  

#### <a name="item-setup" />Настройка товара

|Политика повтора заказа|Максимальное кол-во|  
|-----------------------|------------------|  
|Максимальное количество заказа|100|  
|Точка повтора заказа|50|  
|Запасы|80|  

#### <a name="situation-before-sales-decrease" />Ситуация до снижения продаж

|Событие|Изменить кол-во|Ожидаемые запасы|  
|-----------|-----------------|-------------------------|  
|День первый|Нет|80|  
|Продажа|-70|10|  
|Конец горизонта планирования|Нет|10|  
|Предложение нового возврата покупки|+90|100|  

#### <a name="situation-after-sales-decrease" />Ситуация после снижения продаж

|Изменение|Изменить кол-во|Ожидаемые запасы|  
|------------|-----------------|-------------------------|  
|День первый|Нет|80|  
|Продажа|-40|40|  
|Покупка|+90|130|  
|Конец горизонта планирования|Нет|130|  
|Предложение по уменьшению количества покупки<br><br> заказ с 90 до 60|-30|100|  

#### <a name="resulting-planning-lines" />Результирующие строки планирования

Система создает строка планирования предупреждения для уменьшения количества покупки на 30, с 90 до 60, для соответствия прогнозируемых запасов 100 допустимому избытку.  

![Планирование в соответствии с допустимым избытком.](media/nav_app_supply_planning_2_overflow2.png "Планирование в соответствии с допустимым избытком")  

> [!NOTE]  
> Без функции допустимого избытка никаких предупреждений не создается, если прогнозируемый уровень склада выше максимума, что может привести к дополнительной поставке 30.

## <a name="handling-projected-negative-inventory" />Обработка прогнозируемых отрицательных остатков

Точка повторного заказа выражает предполагаемый спрос во время подготовки товара. Прогнозируемые запасы должны быть достаточно большими для того, чтобы удовлетворить спрос до получения нового заказа. В то же время страховой запас должен устранить колебания в спросе и увеличить количество до целевого уровня обслуживания.  

Система планирования считает чрезвычайной ситуацией, если будущий спрос не может быть обслужен за счет прогнозируемого запаса. Или, выражаясь по-другому, прогнозируемый запас становится отрицательным. Система предлагает создать новый заказ на поставку для покрытия неудовлетворенной части спроса. Размер нового заказа на поставку не будет учитывать максимальный запас или количество повторного заказа, а также следующие модификаторы заказа:

* «Максимальное кол-во заказа»;
* «Минимальное кол-во заказа»;
* «Заказать несколько»; 

Вместо этого он отражен точный дефицит.  

Строка планирования для этого заказа на поставку отобразит предупреждающий значок **Экстренный** с возможностью просмотра дополнительных сведений.  

На следующем рисунке поставка D представляет экстренный заказ для коррекции отрицательных остатков.  

![Предложение экстренного планирования для предотвращения отрицательных остатков.](media/nav_app_supply_planning_2_negative_inventory.png "Предложение экстренного планирования для предотвращения отрицательных остатков")  

1. Поставка **A** (изначально прогнозируемые запасы) ниже точки дозаказа.  
2. Создана новая поставка с прямым планированием (**C**).  

     (количество = максимальный запас - прогнозируемый уровень запасов)  
3. Поставка **A** закрыта спросом **B**, который удовлетворен в полном размере.  

     (Спрос **Б** может попытаться запланировать поставку C, но горизонт планирования предотвращает это.)  
4. Создается новая поставка (**D**) для покрытия оставшегося количества в спросе **B**.  
5. Спрос **B** закрыт (создание напоминания для прогнозируемых запасов).  
6. Новая заявка **D** закрыта.  
7. Прогнозируемые запасы проверены. Точка перезаказа не пройдена.  
8. Поставка **C** закрыта (спрос больше не существует).  
9. Окончательная проверка. Необработанных напоминаний об уровне запасов нет.  

В следующем разделе описываются характеристики четырех поддерживаемых политик повторного заказа.

## <a name="reordering-policies" />Политики дозаказа

Политики дозаказа определяют количество для заказа, если необходимо пополнить товар. Существует четыре различные политики дозаказа.  

### <a name="fixed-reorder-quantity" />Фиксированное кол-во для дозаказа

Политика фиксированное количество повторного заказа обычно используется для планирования запасов товаров со следующими характеристиками:

* Низкая себестоимость запасов
* Низкий риск устаревания
* Низкое количество товаров

Как правило, эту политику следует использовать с точкой повторного заказа, которая отражает ожидаемый спрос в течение времени подготовки заказа.  

#### <a name="calculated-per-time-bucket" />Расчет на горизонт планирования

Если вы достигаете или пересекаете точку повторного заказа в горизонт планирования (цикл повторного заказа), система предлагает два действия:

* Создать новый заказ на поставку для количества дозаказа
* Планирование заказа заранее с первой даты после окончания горизонт планирования  

Точка повторного заказа в горизонт планирования уменьшает число предложений поставки. Она отражает процесс ручной проверки фактического содержимого ячеек на вашем складе.  

#### <a name="creates-only-necessary-supply" />Создание только необходимой поставки

Прежде чем предложить новый заказ на поставку для достижения точки повторного заказа, система планирования проверяет следующие поставки:

* Заказана ли поставка
* Ожидаете ли вы получить поставку в течение времени подготовки товара

Система не будет предлагать новый заказ на поставку, если поставка доставит запланированные запасы в точку повторного заказа в течение времени подготовки.  

Заказы на поставку, созданные специально для соответствия точке дозаказа, исключаются из балансировки поставки и не изменятся. Если вы хотите поэтапно отказаться от товара, для которого есть точка повторного заказа, просмотрите незавершенные заказы на поставку вручную или измените политику повторного заказа на **Партия на партию**. Система уменьшит или отменит дополнительную поставку.  

#### <a name="combines-with-order-modifiers" />Объединение с модификаторами заказа

Модификаторы заказов Минимальное кол-во заказа, Максимальное кол-во заказа и Заказать несколько не должны играть существенной роли при использовании политики фиксированного количества для повторного заказа. Однако система планирования их учитывает:

* Уменьшите количество до указанного максимального количества заказа (и создайте два или более поставок, чтобы достичь общего количества заказа)
* Увеличьте заказ до указанного минимального количества заказа
* Округлите количество заказа, чтобы оно соответствовало указанному множителю заказа  

#### <a name="combines-with-calendars" />Объединение с календарями

Прежде чем предложить новый заказ на поставку для достижения точки повторного заказа, система планирования проверяет, запланирован ли заказ на нерабочий день. Она использует календари, указанные вами в поле **Код базового календаря** на страницах **Информация о компании** и **Карточка склада**.  

Если плановая дата является нерабочим днем, система планирования переместит заказ до ближайшего рабочего дня. Смещение даты может привести к тому, что заказ достигнет точки повтора заказа, но не удовлетворит определенному спросу. Если такого несбалансированного спроса система планирования создает дополнительную поставку.  

#### <a name="shouldnt-be-used-with-forecasts" />Не для использования с прогнозами

Поскольку ожидаемый спрос уже выражен на уровне точки дозаказа, не обязательно включать прогноз в планирование товара. Если политика "**Партия на партию**" имеет отношение к созданию плана на основе прогноза, используйте ее.  

#### <a name="must-not-be-used-with-reservations" />Не для использования с резервированиями

Если вы резервировали количество, например количество в запасах, для отдаленного спроса, основа планирования может быть нарушена. Даже если прогнозируемый уровень запасов является приемлемым в отношении точки дозаказа, количества могут быть недоступны. Система может попытаться компенсировать это, создав исключительные заказы. Однако мы рекомендуем, чтобы в поле **Резервировать** было установлено значение **Никогда** для товаров, запланированных с использованием точки повторного заказа.

### <a name="maximum-quantity" />Максимальное количество

Политика максимального количества — это способ ведения запасов с использованием точки повтора заказа.  

Все, что имеет отношение к политике "Фикс. кол-во дозаказа", также применяется к этой политике. Единственное отличие — в количестве предлагаемой поставки. При использовании политики максимального количества, количество повторного заказа определяется динамически с учетом прогнозируемого уровня запасов. Как правило, от заказа к заказу это количество различается.  

#### <a name="calculate-per-time-bucket" />Расчет на горизонт планирования

Когда вы достигаете точки повторного заказа или пересекаете ее, система определяет объем повторного заказа в конце горизонт планирования. Система измеряет разницу между текущим прогнозируемым уровнем запасов и указанным максимальным запасом, чтобы определить количество для заказа. Затем система проверяет:

* Заказана ли поставка
* Ожидаете ли вы получить поставку в течение времени подготовки товара

Если это так, система уменьшает количество нового заказа на поставку на уже заказанные количества.  

Если вы не укажете максимальное количество запасов, система планирования гарантирует, что прогнозируемый запас достигнет количества повторного заказа.

#### <a name="combine-with-order-modifiers" />Объедините с модификаторами заказа

В зависимости от вашей настройки может быть лучше объединить политику максимального количества с модификаторами заказа: 

* Чтобы обеспечить минимальное количества заказа
* Округлить количество до целого числа единиц измерения покупки
* Разделите количество на партии в соответствии с максимальным количеством заказа  

### <a name="combine-with-calendars" />Объедините с календарями

Прежде чем предложить новый заказ на поставку для достижения точки повторного заказа, система планирования проверяет, запланирован ли заказ на нерабочий день. Она использует календари, указанные вами в поле **Код базового календаря** на страницах **Информация о компании** и **Карточка склада**.  

Если плановая дата является нерабочим днем, система планирования переместит заказ до ближайшего рабочего дня. Смещение даты может привести к тому, что заказ достигнет точки повтора заказа, но не удовлетворит определенному спросу. Если такого несбалансированного спроса система планирования создает дополнительную поставку.

### <a name="order" />Порядок

В среде изготовления продукции на заказ товар приобретается или производится для удовлетворения определенного спроса. Обычно политика повторного заказа Заказ используется для товаров со следующими характеристиками

* Спрос нечастый
* Время подготовки незначительно
* Требуемые атрибуты различаются  

[!INCLUDE [prod_short](includes/prod_short.md)] создает связь "заказ-в-заказ", которая действует как основное соединение между поставкой (заказом на поставку или запасом) и спросом. Вы можете применить связь "заказ-в-заказ" во время планирования следующими способами:  

* При использовании политики производства на заказ для создания многоуровневых производственных заказов или заказов проектного типа (производство необходимых компонентов в одном производственном заказе)  
* При использовании планирования заказа на продажу для создания производственного заказа из заказа на продажу  

> [!TIP]
> Если атрибуты товара не изменяются, может быть лучше использовать политику переупорядочивания "Партия на партию". В результате, система использовать незапланированный запас и накапливать только заказы на продажу с одинаковой датой отгрузки или заказы на продажу в пределах указанного горизонта планирования.  

#### <a name="order-to-order-links-and-past-due-dates" />Связи "заказ-в-заказ" и просроченные даты

В отличие от большинства наборов спрос-предложение, связанные заказы с датами оплаты до даты начала планирования полностью планируются системой. Причина этого исключения следующая: конкретные наборы спроса и предложения должны синхронизироваться. Дополнительные сведения о замороженной зоне, применяемой к большинству типов поставки и спроса, см. в разделе [Обработка заказов до даты начала планирования](design-details-balancing-demand-and-supply.md#process-orders-before-the-planning-start-date).

### <a name="lot-for-lot" />Партия на партию

Политика "партия на партию" является наиболее гибкой, поскольку система реагирует только на фактический спрос. Она действует в соответствии с ожидаемым спросом из прогнозируемых и общих заказов, а затем сопоставляет количество заказа с учетом спроса. Политика ориентирована на товары, где запасы могут быть приняты, однако этого следует избегать.  

В некотором смысле политика "партия на партию" похожа на политику "Заказ", но она имеет общий подход к товарам. Она может принимать количества в запасах и связывать спрос и предложение в определенные вами горизонты планирования.  

Горизонт планирования указывается в поле **Горизонт планирования** на странице **Карточка товара** . Минимальный размер горизонта планирования составляет один день, поскольку это наименьшая единица измерения времени для событий спроса и предложения в [!INCLUDE [prod_short](includes/prod_short.md)].  

Горизонт планирования также устанавливает лимиты перепланирования заказа на поставку с целью удовлетворения имеющегося спроса. Поставка в пределах горизонта планирования будет перепланирована на более раннюю или позднюю дату, чтобы удовлетворить спрос. Более ранняя поставка вызовет дополнительные запасы, и вы должны отменить ее. Для поставки позже создайте новый заказ на поставку.  

С помощью этой политики вы можете указать страховой запас, чтобы компенсировать изменения в поставке или удовлетворить внезапный спрос.  

Поскольку объем заказа на поставку основан на фактическом спросе, имеет смысл использовать модификаторы заказа:

* Округлите количество заказа, чтобы оно соответствовало множителю заказа (или единице измерения покупки)
* Увеличьте заказ до указанного минимального количества заказа
* Уменьшите количество до указанного максимального количества (и создайте два или более поставок, чтобы достичь нужного общего количества)

## <a name="see-also" />См. также

[Сведения о проектировании: параметры планирования](design-details-planning-parameters.md)  
[Сведения о проектировании: таблица "Назначение произ. плана"](design-details-planning-assignment-table.md)  
[Сведения о проектировании: основные понятия системы планирования](design-details-central-concepts-of-the-planning-system.md)  
[Сведения о проектировании: балансировка спроса и поставки](design-details-balancing-demand-and-supply.md)  
[Сведения о проектировании: планирование поставок](design-details-supply-planning.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
