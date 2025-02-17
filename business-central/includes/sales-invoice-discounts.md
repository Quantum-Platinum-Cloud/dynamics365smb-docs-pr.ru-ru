---
author: brentholtorf
ms.topic: include
ms.date: 10/05/2022
ms.author: bholtorf
---
После добавления всех товаров в строках вы можете рассчитать скидку по счету для всего документа продаж, выбрав действие **Вычислить скидку по счету**.

Скидка рассчитывается на основе всех строк документа продаж, в которых установлен флажок **Разрешить скидку по счету**. По умолчанию скидки по счету разрешены. Однако строки с товарными издержками, например, не включаются в расчет скидки по счету. Чтобы применить скидку к таким строкам, введите значение в поле **Сумма скидки строки** в этих строках.  

> [!NOTE]
> По умолчанию поля **Разрешить скидку по счету** и **Сумма скидки строки** в строках скрыты. Если эти поля недоступны, вы можете добавить их, персонализировав страницу. Дополнительные сведения см. в разделе [Персонализация рабочей области](../ui-personalization-user.md#to-start-personalizing-a-page-through-the-personalizing-banner).

> [!TIP]
> Если поле **Расчет скидки по счету** выбрано на странице **Настройка модуля "Продажи"**, скидка по счету вычисляется автоматически. То, когда происходит вычисление, зависит от типа используемого документа продажи.
>
> Если вы используете заказ на продажу, скидка рассчитывается при добавлении строки. Для всех других документов продажи, таких как счета по продажам, скидка рассчитывается при выполнении любого из следующих действий:
>
> * Просмотр статистики
> * Просмотр тестового отчета
> * Печать
> * Почта

Условия предоставления скидки для клиента задаются на странице **Скидки по счету клиента**. Код валюты в документе продажи используется для поиска условий предоставления скидки по счету в соответствующей валюте.

Если вы не определили скидки по счету для иностранных валют, для расчета скидки используются условия скидки на странице **Скидки по счету клиента**. При расчете используется ваша местная валюта и обменный курс, действовавший на дату учета документа.
