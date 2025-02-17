---
title: Сведения о проектировании — трассировка и планирование товара | Документация Майкрософт
description: 'Поскольку они хранятся в системе резервирования, номера трассировки товара полностью согласовываются с записями трассировки заказов.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/08/2021
ms.author: edupont
---
# <a name="design-details-item-tracking-and-planning" />Сведения о проектировании: трассировка и планирование товара
Поскольку они хранятся в системе резервирования, номера трассировки товара полностью согласовываются с записями трассировки заказов. Это означает, что товарам с записями трассировки заказов можно присвоить номера трассировки заказов. И наоборот, товары с номерами трассировки товара могут стать записями трассировки заказов. Дополнительные сведения см. в разделе [Сведения о проектировании: проектирование трассировки товара](design-details-item-tracking-design.md).

Дополнительные сведения об интегрированных системах см. в разделе [Сведения о проектировании: резервирование, трассировка заказов и отправка сообщений о действиях](design-details-reservation-order-tracking-and-action-messaging.md).

Поскольку трассировка заказов связана только с определенным применением товара, согласование с номерами трассировки товара применяется только для товаров, настраиваемых для использования определенной трассировки товаров. Это установлено полями **Трассировка СН** и **Партия - трассировка** на карточке товара, в которых указано следующее:

- Товар должен иметь серийный номер или номер партии при учете.
- Товар также необходимо применить к тому же серийному номеру или номеру партии при исходящем учете.

В соответствии со стандартными принципами балансировки поставки и спроса система планирования и связанная функция трассировки заказов сопоставляют поставку и спрос с номерами трассировки товара, только если данный товар использует определенную трассировку товаров. Во всех остальных случаях системы планирования и трассировки заказов игнорируют номера трассировки товара при применении поставки для удовлетворения спроса или при применении спроса к поставке. Дополнительные сведения см. в разделе [Сведения о проектировании: резервирование, трассировка заказов и отправка сообщений о действиях](design-details-reservation-order-tracking-and-action-messaging.md).

Например, если выполняется трассировки заказа для данного товара, это значит, что записи по товару уже находятся в таблице **Операция резервирования**, которая является основой системы резервирования, до определения номеров трассировки. Следовательно, следующие ограничения связывания применяются к номерам трассировки товаров в трассируемом заказе:

- Спрос с серийным номером или номером партии может покрывать поставку только с тем же серийным номером или номером партии.
- Спрос без серийного номера или номера партии может покрывать любую поставку с серийным номером или номером партии либо без них.

Помимо последствий для динамической трассировки заказов ограничения на объединение трассировки товаров не влияют на систему планирования в значительной степени.

На стороне поставки серийный номер или номер партии обычно не вводится до момента непосредственно перед учетом заказа, например приходной накладной покупки на складе. При вводе на стороне спроса серийного номера или номера партии, например заказа на продажу, этот серийный номер или номер партии уже находится на складе. Соответственно, номера трассировки товара обычно не вызывают проблем при планировании поставок.

В случае товаров, для которых используется определенная трассировка товаров, весь спрос, включающий серийные номера или номера партий, должен быть сопоставлен с соответствующей поставкой. В большинстве случаев не имеет смысл дозаказывать определенный серийный номер или номер партии, поскольку планирование покупки или производственных поставок, вероятно, не затрагивается. Однако при перемещении товаров из одного склада на другой имеется вероятность того, что это перемещение выполняется для определенной партии, поэтому на планирование перемещения поставок может влиять определенное ограничение на объединение.

Дополнительные сведения см. в разделе [Сведения о проектировании: перемещения при планировании](design-details-transfers-in-planning.md).

## <a name="balancing-demand-and-supply" />Балансировка спроса и поставки
Если для товара требуется определенная трассировка товаров, создается связь трассировки заказа, ведущая от всего спроса трассировки товара к любой соответствующей поставке трассировки товара. Единственное ограничение заключается в том, что поставка должна следовать до спроса. Если при таких обстоятельствах невозможно найти поставку трассировки товара, соответствующую спросу с включенной трассировкой товаров, сразу же создается новая поставка трассировки товара без учета размеров заказа, параметров планирования или перепланирования существующей поставки с тем же серийным номером или номером партии.

Если номера трассировки товара назначаются на стороне спроса или на стороне поставки без определенной трассировки товаров, создается связь трассировки заказов, ведущая от спроса к поставке, на основе наиболее подходящего времени и количества, как при выполнении обычной процедуры балансировки. Заданный номер трассировки товаров отправляется в запись трассировки заказа так же, как определенное количество трассировки товаров определяет один конец связи трассировки заказа. Это означает, что вводимый номер трассировки товаров сохраняется, хотя он также является частью записи трассировки заказов.

Если номера трассировки товара назначаются на стороне поставки без определенной трассировки товаров, эта поставка считается фиксированной в системе планирования. Перепланирование или изменение размера не предлагаются для данной поставки, но поставка учитывается, когда система планирования пытается удовлетворить общие потребности.

Дополнительные сведения см. в разделе [Сведения о проектировании: балансировка спроса и поставки](design-details-balancing-demand-and-supply.md).  

## <a name="see-also" />См. также
[Сведения о проектировании: разработка трассировки товара](design-details-item-tracking-design.md)  
[Сведения о проектировании: балансировка спроса и поставки](design-details-balancing-demand-and-supply.md)  
[Сведения о проектировании: резервирование, трассировка заказов и отправка сообщений о действиях](design-details-reservation-order-tracking-and-action-messaging.md)   
[Сведения о проектировании: планирование поставок](design-details-supply-planning.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
