---
title: Включение платежей клиентов через службу платежей
description: 'Облегчите клиентам оплату счетов, включив платежи клиентов через службы платежей.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: online payment
ms.search.forms: '1060, 1061, 1062'
ms.date: 06/25/2021
ms.author: edupont
---
# <a name="enable-customer-payments-through-payment-services" />Включение платежей клиентов через службу платежей

В качестве альтернативы сбору платежей через банковские переводы или кредитные карты вы можете предложить клиентам оплату через учетную запись в службе платежей, например PayPal или WorldPay.  

После включения службы платежей в [!INCLUDE[prod_short](includes/prod_short.md)] станет доступна ссылка на службу в документах продажи, отправляемых по электронной почте клиентам. Клиенты могут использовать эту ссылку для перехода к службе платежей и оплаты счетов непосредственно из документа продажи. Если не требуется включать ссылку, например если клиент платит наличными деньгами, можно удалить службу платежей из счета до учета.  

Расширения PayPal Payments Standard и WorldPay Payments Standard установлены в [!INCLUDE[prod_short](includes/prod_short.md)] и готовы к включению.  

## <a name="to-enable-a-payment-service-in-includeprodshortincludesprodshortmd" />Включение службы платежей в [!INCLUDE[prod_short](includes/prod_short.md)]

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Службы платежей**, а затем выберите связанную ссылку.  
2. На странице **Службы платежей** выберите действие **Создать**.  
3. Выберите службу платежей, затем закройте страницу.  
4. На странице **Службы платежей** выберите действие **Настройка**.  
5. Заполните соответствующим образом поля. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
6. Закройте страницу.  

## <a name="to-select-a-payment-service-on-a-sales-invoice" />Выбор службы платежей в счете продажи

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Счета продажи**, а затем выберите связанную ссылку.  
2. Откройте счет продажи, который необходимо оплатить с помощью службы платежей.  
3. В поле **Служба платежей** выберите службу платежей.  

    > [!NOTE]  
    > Поле **Служба платежей** доступно, только если включена служба платежей.  

## <a name="see-related-microsoft-trainingtrainingmodulescash-management-dynamics-365-business-central" />См. соответствующее [обучение Microsoft](/training/modules/cash-management-dynamics-365-business-central/)

## <a name="see-also" />См. также

[Настройка продаж](sales-setup-sales.md)  
[Продажи](sales-manage-sales.md)  
[Настройка [!INCLUDE[prod_short](includes/prod_short.md)] с помощью расширений](ui-extensions.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
