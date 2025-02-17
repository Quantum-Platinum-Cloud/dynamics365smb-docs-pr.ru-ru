---
title: Настройка способов оплаты (содержит видео)
description: 'Способы оплаты, например, чеки, банковские переводы, наличные или PayPal используются для того, чтобы определять, как именно должны оплачиваться счета на продажу и покупку.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'check, bank transfer, cash, PayPal'
ms.search.form: 427
ms.date: 04/01/2021
ms.author: bholtorf
---
# <a name="set-up-payment-methods" />Настройка способов оплаты

Методы оплаты определяют предпочтительный способ, которым клиенты осуществляют платежи вам, и способ, которым вы хотите платить поставщикам. Метод может меняться для каждого клиента или поставщика. Типичными примерами методов оплаты являются **банк**, **касса**, **чек** или **счет**.

Можно назначить метод оплаты клиентам и поставщикам, чтобы один и тот же метод всегда использовался в документах продаж и покупки, создаваемых для них. При необходимости можно изменить метод в документе продажи или покупки. Например, если требуется оплатить конкретный счет на покупку наличными, а не чеком. Это не изменяет метод оплаты по умолчанию, назначенный поставщику.

Эти же способы платежа используются для документов покупки и продажи. Например, способ платежа _касса_ используется как при осуществлении платежей, так и при получении платежей. [!INCLUDE[prod_short](includes/prod_short.md)] знает, что при создании счета продажи ожидается получение платежа, и оплата наоброт для счетов покупки.

Кредит-ноты для возвратов, однако, являются исключениями, поскольку денежные средства передаются в противоположных направлениях, от вас клиенты и от вашего поставщика вам. Поэтому способ платежа по умолчанию не назначается кредит-нотам. Имеется, однако, обходной способ, если вы указали условия платежа для клиента или поставщика. Хотя поле **Расчет скидки оплаты по кредит-нотам** не предназначено для этого, если установить флажок **Условия платежа**, метод оплаты по умолчанию будет добавлен при создании кредит-ноты. <br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE476Ys?rel=0]

## <a name="to-set-up-a-payment-method" />Настройка метода оплаты

[!INCLUDE[prod_short](includes/prod_short.md)] обеспечивает несколько способов платежа, которые часто используются организациями. Можно, однако, добавить любое необходимое число.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Способы оплаты**, а затем выберите связанную ссылку.
2. Заполните соответствующим образом поля. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

При желании добавьте условия оплаты для вашего способа оплаты. Дополнительные сведения см. в разделе [Настройка условия платежа](finance-payment-terms.md).  

## <a name="to-assign-a-payment-method-to-a-customer-or-vendor" />Присвоение метода платежа клиенту или поставщику

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Клиент** или **Поставщик**, а затем выберите связанную ссылку.
2. В поле **Код способа оплаты** выберите метод, который будет использоваться по умолчанию для клиента или поставщика.

## <a name="see-related-microsoft-trainingtrainingmodulescash-management-dynamics-365-business-central" />См. соответствующее [обучение Microsoft](/training/modules/cash-management-dynamics-365-business-central/)

## <a name="see-also" />См. также

[Регистрация новых клиентов](sales-how-register-new-customers.md)  
[Настройка условия платежа](finance-payment-terms.md)  
[Финансы](finance.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
