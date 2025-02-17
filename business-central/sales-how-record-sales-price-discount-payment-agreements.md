---
title: Регистрация специальных цен продажи и скидок
description: 'Описывает, как задавать соглашения о ценообразовании и скидках для документов продажи.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: ivkoleti
ms.topic: how-to
ms.date: 06/13/2023
ms.custom: bap-template
ms.search.keywords: 'special price, alternate price, pricing'
ms.search.form: '7022, 7024'
---

# Регистрация специальных цен продажи и скидок

> [!NOTE]
> Во 2-й волне выпуска 2020 года представлены новые улучшенные процессы для настройки цен и скидок и управления ими. Если вы новый клиент, использующий последнюю версию, вы используете новый интерфейс. Если вы уже являетесь клиентом, то используете ли вы новый интерфейс, зависит от того, включил ли ваш администратор обновление функции **Новые возможности ценообразования для продажи** в **Управление функциями**. Подробнее см. в разделе [Раннее включение новых функций](/dynamics365/business-central/dev-itpro/administration/feature-management) в материалах по администрированию.

[!INCLUDE[prod_short](includes/prod_short.md)] поддерживает различные стратегии ценообразования, такие как:

* Модели с одной ценой для всех, когда товар всегда продается по одной и той же цене.
* Специальные ценовые соглашения с конкретными клиентами или группами клиентов.
* Кампании, когда продажа соответствует критериям специального предложения. Например, у вас могут быть следующие критерии для заказа:

  * Соответствует минимальному количеству
  * Размещен до определенной даты
  * Включает определенный тип товаров  

Чтобы использовать базовую модель ценообразования, вам нужно только указать цену за единицу при настройке товара или ресурса. Эта цена всегда будет использоваться в документах продажи. Для более продвинутых моделей, например, когда вы хотите предложить специальные цены для кампании продаж, вы можете указать критерии на странице **Цены продажи**. Вы можете предложить специальные цены, основанные на комбинации следующих сведений:  

* Клиент
* Товар
* Единица измерения
* Минимальное количество
* Даты, определяющие период действия цен.

После того как вы установите специальные цены, [!INCLUDE[prod_short](includes/prod_short.md)] может рассчитывать лучшие цены в документах продажи и покупки, а также в строках заданий и журналов товаров. Узнайте больше в разделе [Расчет лучшей цены](sales-how-record-sales-price-discount-payment-agreements.md#best-price-calculation).

Для скидок продажи вы можете настроить два типа:

| Тип скидки | Описанием |
| --- | --- |
| **Скидки строки продаж** |Позволяет добавить сумму в строки продаж, которые содержат определенное сочетание клиента, минимального количества, единицы измерения или дат начала и окончания. Этот тип работает так же, как и для цен продажи. |
| **Скидка по счету** |Процент скидки, который вычитается из общей суммы документа продажи, если сумма всех строк документа превышает определенный минимум. |

> [!TIP]  
> Если требуется, чтобы товар никогда не продавался со скидкой, просто оставьте поля скидки на странице товара пустыми и не включайте товар ни в какую настройку строки скидки.

## Настройка цены продажи для клиента

Эти шаги различаются в зависимости от того, включил ли ваш администратор обновление функции **Новые возможности ценообразования для продажи**. Если обновление функции не включено, следуйте инструкциям на вкладке "Текущая версия". 

#### [Текущая версия](#tab/current-experience/)

1. Выберите значок ![Лампочка, которая открывает функцию "Что вы хотите сделать"](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Клиенты**, затем выберите соответствующую ссылку.
2. Выберите клиента и выберите действие **Цены**.
3. Заполните поля в строке по мере необходимости. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Заполните строку для каждой комбинации, которая предоставляет клиенту специальную цену.

#### [Новая версия](#tab/new-experience/)  

По умолчанию статус новых прайс-листов — **Черновик**. Черновые прайс-листы не включаются в расчет цен. Когда вы закончите добавлять строки и хотите начать использовать цены, измените статус на **Активный**.

1. Выберите значок ![Лампочка, которая открывает функцию "Что вы хотите сделать"](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Клиенты**, затем выберите соответствующую ссылку.
2. Выберите клиента, затем выберите действие **Прайс-листы продажи**. 
3. Выберите **Создать** для создания нового прайс-листа.
4. На экспресс-вкладках **Общее** и **Налог** заполните необходимые поля. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Чтобы добавить элементы в список, выполните одно из следующих действий:
   * Чтобы добавить много элементов, выберите **Предложить строки**, а затем введите критерии фильтрации, чтобы указать типы добавляемых элементов. При желании вы также можете ввести некоторые другие настройки для номенклатур, относящихся к прайс-листу. Если требуется, эти настройки можно изменить позднее.
   * Чтобы скопировать номенклатуры из другого прайс-листа, выберите **Копировать строки**, а затем выберите прайс-лист для копирования.
   * Чтобы добавить элементы вручную, в сетке в поле **Тип продукта** выберите тип продукта, на который рассчитан прайс-лист. В зависимости от выбора заполните остальные поля. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Чтобы начать пользоваться прайс-листом, в поле **Состояние**, выберите **Активный**.  

---

## Использование прайс-листов продаж и покупки

> [!NOTE]
> Для использования прайс-листов необходимо, чтобы ваш администратор включил обновление функции **Новые возможности ценообразования для продажи** в **Управление функциями**. Подробнее см. в разделе [Раннее включение новых функций](/dynamics365/business-central/dev-itpro/administration/feature-management) в материалах по администрированию.

Большая часть нового интерфейса ценообразования продаж похожа на текущую версию, но есть несколько отличий. Эти отличия описываются в следующих разделах.

Поля **Применяется к типу** и **Применяется к №** позволяют выбрать, к чему будет применяться прайс-лист, например, клиенту или ценовой группе клиента. С помощью **Показывать столбцы для** вы можете показать или скрыть столбцы, относящиеся к настройке цен, скидок или цен и скидок.

### Преобразование существующих цен при включении обновления функции ценообразования

Когда вы включаете обновление функции **Новые возможности ценообразования для продажи** на странице **Управление функциями**, откроется руководство **Обновление данных функционального компонента**. Используйте переключатель **Использовать цены по умолчанию** следующим образом:

* Если вы хотите работать со всеми ценами на одной странице, включите его. Существующие цены конвертируются в один прайс-лист по умолчанию для каждого из следующих документов:

  * Продажи
  * Покупки
  * Выручка от реализации услуг
  * Покупки работы

  Вы можете редактировать все цены для этих областей на странице **Лист цен**. Прайс-листы по умолчанию устанавливаются на страницах **Продажи и дебитор. задолж.**, **Покупки и кредиторская задолженность** и **Настройка работ**.

> [!NOTE]
> Если цены установлены только для карточек товаров или ресурсов, прайс-листы по умолчанию не будут заполняться этими ценами во время обновления данных. Однако вы можете открыть любой прайс-лист по умолчанию или страницу **Лист цен** и использовать действие **Предложить строки**, чтобы добавить цены, установленные для карточек товаров или ресурсов.

* Чтобы использовать прайс-листы со скидкой, отключите его. Существующие цены будут преобразованы в новый прайс-лист по каждой комбинации для следующих категорий:

  * Клиент
  * Группа клиентов или кампания
  * Даты начала и окончания
  * Валюты

Если у вас много комбинаций, у вас будет много прайс-листов.

Если вы уже включили новый вариант ценообразования, вы можете создать прайс-листы по умолчанию вручную или указать существующий прайс-лист по умолчанию. Чтобы установить существующий прайс-лист по умолчанию, включите переключатель **Разрешить обновление значений по умолчанию** на прайс-листе. Затем на страницах **Настройка модуля Продажи и дебитор. задолж.**, **Покупки и кредиторская задолженность** или **Настройка работ** задайте прайс-лист как по умолчанию.

### Редактирование активных прайс-листов

Чтобы люди могли редактировать цены в активных прайс-листах для товаров, ресурсов, клиентов, поставщиков или других организаций, которые используют цены, включите переключатель **Разрешить редактирование активной цены** на странице **Настройка Продажи и дебитор. задолж.** и **Настройка Покупка и кредиторская задолженность**.

Когда переключатель **Разрешить редактирование активной цены** выключен, для обновления цен в прайс-листе необходимо изменить статус прайс-листа на **Черновик**, внесите изменения, а затем повторно активируйте прайс-лист.

На странице **Обзор цен** представлен обзор всех цен в прайс-листах. Вы можете установить фильтры, чтобы сузить список цен, которые вы хотите изменить или добавить. После изменения цен вы должны использовать действие **Проверить строки** для проверки цен по другим строкам прайс-листа. Проверка цен помогает избежать дублирования и двусмысленности при расчете цен.

> [!NOTE]
> Когда вы редактируете строку в активном прайс-листе, статус строки становится **Черновиком**, и строка не будет учтена при расчете цены до тех пор, пока вы не воспользуетесь действием **Проверить строки**. После того, как вы проверите цену, строка станет **Активной** и будет учитываться при расчете цен.

Чтобы добавить новые цены, на странице **Обзор цен**, используйте действие **Добавить новые строки**. Открывается страница **Лист цен** и вы можете добавить строки цен, предложив их на основе критериев, скопировав их из других прайс-листов или введя их вручную. После этого вы можете использовать действие **Выполнение изменений цен** для сравнения новых цен с другими прайс-листами, чтобы избежать дублирования и двусмысленности при расчете цен.

#### Создание строк цены продажи на основе цены за единицу

1. На странице **Лист цен** выберите действие **Предложить строки**.
2. На странице **Строки цен — Создать** заполните требуемые поля. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. В поле **Фильтр продуктов**, определите фильтры для выбранного **Типа продукта**.
4. Выберите поле **По умолчанию** для указания таких параметров, как:
   * Каким сущностям будет присвоен прайс-лист.
   * Даты, когда цена действительна.
   * Код валюты.
   * Фильтр по типу суммы, от которого зависят столбцы, отображаемые в строках прайс-листа.
5. Выберите **ОК**. Новые строки будут добавлены в страницу **Лист цен** с выбранными настройками и ценами за единицу из карточек товаров.
6. Отредактируйте созданные строки с новыми ценами за единицу или скидками. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

#### Создание строк цены продажи на основе существующих прайс-листов

1. На странице **Лист цен** выберите действие **Копировать строки**.
2. На странице **Строки цен — копировать существующие** выберите существующий прайс-лист в поле **Из прайс-листа**.
3. В поле **Фильтр строк цен** определите фильтры для продуктов в выбранном прайс-листе.
4. Выберите поле **По умолчанию** для указания таких параметров, как:
   * Каким сущностям будет присвоен прайс-лист.
   * Даты, когда цена действительна.
   * Код валюты.
   * Фильтр по типу суммы, от которого зависят столбцы, отображаемые в строках прайс-листа.
5. Заполните соответствующим образом другие поля. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
6. Выберите **ОК**. Новые строки будут добавлены на страницу **Лист цен** с выбранными настройками.
7. Отредактируйте созданные строки с новыми ценами за единицу или скидками. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Копирование цен продажи

Эти шаги различаются в зависимости от того, включил ли ваш администратор обновление функции **Новые возможности ценообразования для продажи**. Если обновление функции не включено, следуйте инструкциям на вкладке "Текущая версия".

#### [Текущая версия](#tab/current-experience/)  

Если требуется копировать цены продажи, например, цены продажи отдельного клиента в целях использования этих цен для ценовой группы клиента, то необходимо запустить пакетное задание **Предл. цены продажи в журнале** Пакетное задание на странице **Журнал цен продажи**.  

1. Выберите значок ![Лампочка, которая открывает функцию "Что вы хотите сделать"](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Журнал цен продажи**, затем выберите соответствующую ссылку.  
2. Выберите **Предл. цены продажи в журнале**. .  
3. На экспресс-вкладке **Цены продажи** введите в полях **Тип продажи** и **Код продажи** исходные цены продажи, которые нужно скопировать.  
4. В верхней секции страницы запроса в полях **Тип продажи** и **Код продажи** укажите тип и название, соответствующее продаже, в которую нужно скопировать цены продажи.  
5. Если требуется создать новые цены через пакетное задание, установите флажок **Создать новые цены**.  
6. Нажмите кнопку **ОК** для заполнения строк на странице **Журнал цен продажи** предложенными новыми ценами, указав тем самым, что они действительны для выбранного типа продажи.  

   > [!NOTE]  
   > Данное пакетное задание только предоставляет предложения по изменению, но не вносит предложенных изменений. Если предложения являются удовлетворительными, и их нужно применить, то есть вставить на страницу **Цены продажи**, выберите действие **Выполнить изменение цен** на странице **Журнал цен продажи**.

#### [Новая версия](#tab/new-experience/)  

Вы можете указать параметры, которые будут использоваться в прайс-листе:

* Использовать параметры из заголовка копируемого списка.
* Использовать параметры из заголовка, в который выполняется копирование. Чтобы использовать настройки прайс-листа, в который вы копируете цены, активируйте переключатель **Использовать стандартные значения целевого объекта**.

1. Выберите значок ![Лампочка, которая открывает функцию "Что вы хотите сделать"](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Прайс-листы продажи**, затем выберите соответствующую ссылку.
2. Выберите прайс-лист, который нужно скопировать, а затем выберите **Копировать строки**.
3. Заполните соответствующим образом поля. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > У вас не может быть двух товаров с одинаковыми настройками, но разными ценами. В этом случае при активации прайс-листа отобразится сообщение. Вы можете выбрать цену для использования, открыв список и удалив неверную цену.  
  
---

## Пакетное обновление цен товаров

Эти шаги различаются в зависимости от того, включил ли ваш администратор обновление функции **Новые возможности ценообразования для продажи**. Если обновление функции не включено, следуйте инструкциям на вкладке "Текущая версия".

#### [Текущая версия](#tab/current-experience/)

Чтоб массово обновить цены на товары, например, увеличить цены на все товары на некоторый процент, вы можете заполнить страницу Лист цены продажи с помощью следующих пакетных заданий:

* **Предл. цены продажи в журнале** предполагает изменения одним из двух способов:

  * Путем применения поправочного коэффициента к существующим ценам продажи.
  * Путем копирования существующих соглашений о ценах продажи в других клиентов, ценовые группы клиентов или кампании продаж.

* **Предложенные цены товаров в журнале** предполагает изменения одним из двух способов:

  * Путем применения поправочного коэффициента к существующим ценам за единицу на карточках товаров.
  * Путем предложения цен для новых сочетаний валюты, единиц измерения и т. д.

  Это пакетное задание не изменяет цены за единицу товаров.  

1. Выберите значок ![Лампочка, которая открывает функцию "Что вы хотите сделать"](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Журнал цен продажи**, затем выберите соответствующую ссылку.  
2. Выберите **Предложить цены товаров в журнале**. .  
3. На экспресс-вкладке **Товар** заполните поле **Номер** или **Учетная группа запасов** или другие поля с исходными ценами товаров, которые требуется обновить.  
4. В верхней секции страницы запроса в полях **Тип продажи** и **Код продажи** укажите тип и название, соответствующее продаже, в которую нужно скопировать цены продажи.
5. Если необходимо, чтобы пакетное задание автоматически предложило цены товаров, введите корректировку в поле **Коэффициент коррекции**. Например, следует ввести 1,15 в поле **Коэффициент коррекции**, чтобы увеличить цену товара на 15%.  
6. Если требуется создать новые цены через пакетное задание, включите **Создать новые цены**.  
7. Выберите кнопку **ОК**, чтобы заполнить строки на **Листе цены продажи** предложенными новыми ценами.
8. Чтобы реализовать предложения, используйте действие **Выполнить изменение цен**. Пакетное задание создает предложения, но не реализует их. 

#### [Новая версия](#tab/new-experience/)

Чтобы обновить цены на несколько товаров, необходимо создать новый прайс-лист, а затем скопировать строки из существующего прайс-листа. Когда вы копируете строки, вы можете использовать фильтры, чтобы указать, что копировать, и вы можете указать целое или десятичное число в поле **Коэффициент корректировки** для увеличения или уменьшения цены. Состояние прайс-листа должно быть **Черновик**. При необходимости вы можете отключить старый прайс-лист.

> [!NOTE]
> У вас не может быть двух строк с одинаковыми настройками, но разными ценами. В этом случае при активации прайс-листа отобразится сообщение. Вы можете выбрать цену для использования, открыв список и удалив неверную цену.  

---

## Расчет лучшей цены

После записи специальных цен и скидок строки по продажам и покупкам, [!INCLUDE[prod_short](includes/prod_short.md)] рассчитывает лучшую цену в документах продажи и покупки, а также в строках журнала заданий и товаров.

Лучшая цена — это наиболее низкая цена с наиболее высокой допустимой скидкой строки на конкретную дату. [!INCLUDE[prod_short](includes/prod_short.md)] рассчитывает лучшие цены, когда добавляет цену за единицу и процент скидки по строке в строках документа и журнала.

> [!NOTE]  
> Ниже описано, как рассчитывается лучшая цена для продаж. Для покупок расчет аналогичен, но основан на доступных параметрах. Например, группы скидок на товары не поддерживаются для покупки.

1. [!INCLUDE[prod_short](includes/prod_short.md)] проверяются комбинацию клиента, которому выставляется счет, товара, а затем рассчитывает применимую цену за единицу и процент скидки по строке, используя следующие критерии:

    * Имеется ли для данного клиента специальное соглашение по ценами и скидкам, принадлежит ли клиент к группе, по которой указанное соглашение имеет место?
    * Включены ли товар или группа товара со скидкой для строки в какое-либо из этих соглашений по ценам и скидкам?
    * Находится ли дата в диапазоне между начальной и конечной датами соглашения по ценам/скидкам? Для счетов и кредит-нот это дата в поле **Дата учета** в заголовке документа. Для всех остальных документов это дата в поле **Дата заказа** в их заголовках.
    * Указан ли код единицы измерения? Если да, [!INCLUDE[prod_short](includes/prod_short.md)] проверяет наличие цен/скидок с одинаковыми кодами единиц измерения, а также цены/скидки, для которых коды единиц измерения не заданы.

2. [!INCLUDE[prod_short](includes/prod_short.md)] проверяет, применяются ли какие-либо соглашения о цене/скидке к информации в документе или строке журнала. Затем он вставляет применимую цену за единицу и процент скидки по строке, используя следующие критерии:

    * Существует ли требование к минимальному количеству в соглашении по ценам и скидкам, которое выполняется?
    * Существует ли требование к валюте в соглашении по ценам и скидкам, которое выполняется? Если да, вставляется самая низкая цена и самая высокая скидка по строке для этой валюты, даже если бы в местной валюте была бы лучшая цена. Если для указанного кода валюты не имеется соглашения о ценах и скидках, [!INCLUDE[prod_short](includes/prod_short.md)] вставляет наименьшую цену и наибольшую скидку по строке, выраженную в местной валюте.

Если для товара в строке невозможно рассчитать специальную цену, будет вставлена либо последняя прямая себестоимость, либо цена единицы из карточки товара.

## Скидки по счетам продажи и плата за сервисное обслуживание

При использовании скидок счетов итоговая сумма в счете определяет размер предлагаемой скидки. На странице **Скидки счета клиента** можно также добавить в счета плату за обслуживание на определенную сумму.  

Прежде чем вы сможете использовать скидки по продажам, необходимо указать определенную информацию. Вы должны решить следующее:  

* Каким клиентам предоставлять данный тип скидки?  
* Какие проценты скидки использовать?  

Если вы хотите, чтобы скидки по счету рассчитывались автоматически, на странице **Настройка модуля Продажи и дебиторская задолженность** включите переключатель **Расчет скидки по счету**.  

Вы можете указать, будете ли вы предоставлять скидки по счету, если счет соответствует определенным критериям для каждого клиента. Например, если сумма счета достаточно велика. Скидки счета могут быть настроены местной валюте для отечественных или в иностранной валюте для иностранных клиентов.  

Можно связать процент скидки с определенными суммами счетов на страницах **Клиент — скидки по счету** для каждого клиента. Можно ввести любое число процентных ставок. Для каждого клиента может быть настроена своя страница, или же можно связать несколько клиентов с одной и той же страницей.  

Кроме (или вместо) процентов скидок, можно связать с конкретной суммой по счету суммы платы за услуги.  

> [!TIP]  
> Перед вводом этой информации рекомендуется наметить структуру скидок, которые предполагается использовать. При наличии такой структуры вам будет проще определить, кого из клиентов можно привязать к одной и той же странице скидки по счету. Чем меньше страниц требуется настроить, тем быстрее можно вводить базовую информацию.

Для тренировки по скидкам при продаже см. раздел [Настройка скидок для клиентов](/training/modules/customer-discounts-dynamics-365-business-central/index).

### Расчет скидок счета по продажам

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## Настройка скидки строки продажи для клиента

Эти шаги различаются в зависимости от того, включил ли ваш администратор обновление функции **Новые возможности ценообразования для продажи**. Если обновление функции не включено, следуйте инструкциям на вкладке "Текущая версия".

#### [Текущая версия](#tab/current-experience/)  

1. Выберите значок ![Лампочка, которая открывает функцию "Что вы хотите сделать"](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Клиенты**, затем выберите соответствующую ссылку.
2. Откройте соответствующую карточку клиента и выберите действие **Скидки строки**.
3. Заполните поля в строке по мере необходимости. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Заполните строку для каждой комбинации, которая предоставляет клиенту скидку строки продажи.

> [!NOTE]
> Когда вы открываете страницы **Цены продажи** и **Скидки строки продажи** конкретного клиента, поля **Фильтр по типу продаж** и **Фильтр по коду продаж** задаются для клиента и не могут быть изменены или удалены.
>
> Чтобы установить цены или скидки по строке для всех клиентов, ценовой группы клиентов или кампании, необходимо открыть страницы из карточки товара. Для цен продажи также можно использовать страницу **Журнал цен продажи**. Подробнее см. в разделе [Пакетное обновление цен товаров](sales-how-record-sales-price-discount-payment-agreements.md#to-bulk-update-item-prices).  

#### [Новая версия](#tab/new-experience/)  

1. Выберите значок ![Лампочка, которая открывает функцию "Что вы хотите сделать"](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Клиенты**, затем выберите соответствующую ссылку.
2. Выберите клиента, затем выберите действие **Прайс-листы продажи**.
3. Откройте прайс-лист, для которого нужно указать скидку по строке.
4. Создайте новую строку или выберите существующую строку, а затем заполните поля по мере необходимости. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. В поле **Определяет** выберите либо **Цена и скидка**, либо просто **Скидка**. 
6. В поле **Скидка строки (%)** укажите процент скидки.

    > [!TIP]
    > Если вы редактируете существующую строку, вы можете отфильтровать строки, выбрав соответствующий параметр в поле **Показывать столбцы для**.

    > [!NOTE]  
    > Коды скидок по счету представлены существующими карточками клиентов. Это позволяет быстро назначить условия скидки по счету клиентам, выбрав название другого клиента с такими же условиями. Чтобы настроить условия скидки по счету для конкретного клиента, установите в поле **Код скидки по счету** код клиента, а затем перейдите к следующему шагу.

---

## Настройка скидки по счету для клиента

После того, как принято решение, какие клиенты имеют право на скидки по счетам, укажите в код скидок по счетам на страницах карточек клиентов. Затем настройте условия для каждого кода.

1. Выберите значок ![Лампочка, которая открывает функцию "Что вы хотите сделать"](media/ui-search/search_small.png "Что вы хотите сделать"), введите **Клиенты**, затем выберите соответствующую ссылку.
2. Откройте страницу клиента, который имеет право на получение скидок по счетам.
3. В поле **Код скидки по счету** выберите код соответствующих условий скидки по счету, который будет использован программой для вычисления скидок по счету для клиента.

> [!NOTE]  
> Коды скидок по счету представлены существующими карточками клиентов. Это позволяет быстро назначить условия скидки по счету клиентам, выбрав название другого клиента с такими же условиями.

Перейдите к настройке новых условий скидок по счету продажи.

1. На странице **Клиенты** выберите действие **Скидки по счету**. Откроется страница **Клиент - скидки по счету**.
2. В поле **Код валюты** укажите код валюты, к которой применяются условия скидки по счету в строке. Оставьте поле пустым, чтобы установить условия скидки по счету в местной валюте (руб.).
3. В поле **Минимальная сумма** введите минимальную сумму, которая должна быть на счете, чтобы для этого счета была установлена скидка.
4. В поле **Скидка (%)** введите скидку по счету в процентах от суммы счета.
5. Повторите шаги 5–7 для каждой валюты, в которой клиент будет получать отдельную скидку по счету.

## См. соответствующее [обучение Microsoft](/training/modules/manage-sales-prices-dynamics-365-business-central/index)

## См. также

[Настройка продаж](sales-setup-sales.md)  
[Продажи](sales-manage-sales.md)  
[Настройка ценовых групп клиента](sales-how-to-set-up-customer-price-groups.md)  
[Настройка групп скидок клиента](sales-how-to-set-up-customer-discount-groups.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
