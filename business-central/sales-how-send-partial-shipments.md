---
title: Обработка частичных отгрузок
description: Отгрузки заказов на продажу могут быть обработаны в Business Central в виде частичных отгрузок с использованием полей Сведения по доставке и Кол-во для отгрузки.
author: rubenseishima
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: 'shipping advice, partial shipments, partial deliveries, trade, customer sales order'
ms.date: 08/12/2022
ms.author: a-reishima
---
# <a name="process-partial-shipments" />Обработка частичных отгрузок

При частичной отгрузке заказ не отправляется сразу. Например, из заказа на 100 единиц вы отгружаете 40 единиц сразу и 60 позже. Не существует ограничений по количеству отгрузок, которые можно выполнить для заказа.

Однако, прежде чем вы сможете использовать частичные отгрузки в [!INCLUDE [prod_short](includes/prod_short.md)], необходимо указать, что клиент принимает частичные отгрузки, настроив поле **Сведения по доставке** на странице **Карточка клиента**. Также, если клиент обычно принимает только полные поставки, но затем запрашивает или соглашается на частичную поставку для определенного заказа на продажу, можно изменить поле **Сведения по доставке** перед учетом.

По умолчанию [!INCLUDE [prod_short](includes/prod_short.md)] устанавливает в это поле на странице **Карточка клиента** значение **Частично**, что позволяет выполнять частичные отгрузки. Однако, если поле было настроено с указанием значения **Полностью**, то поле **Кол-во для отгрузки** блокируется в заказах на продажу для этого клиента.

[!INCLUDE [order-ship-invoice_md](includes/order-ship-invoice.md)]

## <a name="see-also" />См. также

[Продажа товара с заказом продажи клиента](sales-how-sell-products.md)  
[Отгрузка товаров](warehouse-how-ship-items.md)  
[Выполнение прямых поставок](sales-how-drop-shipment.md)  
[Продажи](sales-manage-sales.md)  
[Подготовка к ведению бизнеса](ui-get-ready-business.md)  
[Администрация](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
