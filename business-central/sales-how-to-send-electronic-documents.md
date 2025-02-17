---
title: Отправка электронных документов
description: 'Узнайте, как использовать Business Central для отправки счетов-фактур и кредит-нот в формате PEPPOL.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/23/2021
ms.author: edupont
---
# <a name="send-electronic-documents" />Отправка электронных документов

Универсальная версия [!INCLUDE[prod_short](includes/prod_short.md)] поддерживает отправку электронных счетов и кредит-нот в формате PEPPOL, который поддерживается крупнейшими поставщиками служб обмена документами. Поставщик службы обмена документами обеспечивает перемещение электронных документов между торговыми партнерами. Чтобы обеспечить поддержку других форматов электронных документов, следует использовать платформу обмена данными.  

 В универсальной версии [!INCLUDE[prod_short](includes/prod_short.md)] служба обмена документами предварительно сконфигурирована и готова для настройки в вашей компании. Дополнительные сведения см. в разделе [Настройка службы обмена документами](across-how-to-set-up-a-document-exchange-service.md). Однако в некоторых случаях необходимо установить приложение. Дополнительные сведения см. в разделе [Вопросы и ответы по электронному выставлению счетов](faq-electronic-invoicing.yml).  

 Чтобы отправить счет продажи как электронный документ PEPPOL, следует выбрать параметр **Электронный документ** в диалоговом окне **Учет и отправка**. Также можно настроить профиль отправки документов клиента по умолчанию из этого диалогового окна. Прежде всего, необходимо настроить различные основные данные – такие как информацию об организации, клиентах, товарах и единицах измерения. Они используются для определения бизнес-партнеров и товаров при преобразовании данных в полях в разделе [Настройка отправки и получения электронных документов](across-how-to-set-up-electronic-document-sending-and-receiving.md).  

### <a name="to-send-an-electronic-sales-invoice" />Отправка электронного счета продажи

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Счета продажи**, а затем выберите связанную ссылку.  

2. Создайте новый счет продажи.  

3. Когда строки счета продажи готовы к выставлению счета, выберите действие **Учесть и отправить**.  

     Если профиль отправки по умолчанию клиента — **Электронный документ**, то он будет показан в диалоговом окне **Подтверждение учета и отправки**. Таким образом, вам просто нужно выбрать кнопку **Да**, чтобы учесть и отправить счет в электронном виде в выбранном формате.  

4. В диалоговом окне **Подтверждение учета и отправки** нажмите кнопку AssistEdit справа от поля **Кому отправить документ**.  

5. В диалоговом окне **Кому отправить документ** в поле **Электронный документ** выберите **Через службу обмена документами**.  

6. В поле **Формат** выберите **PEPPOL**.  

7. Нажмите кнопку **ОК**. Откроется диалоговое окно **Подтверждение учета и отправки**. **Электронный документ (PEPPOL)** будет добавлен в поле **Кому отправить документ**.  

8. Нажмите кнопку **Да**.  

     Счет продажи учтен и отправлен клиенту в формате PEPPOL.  

    > [!NOTE]  
    >  Можно также отправить учтенный счет на продажу в виде электронного документа. Процедура аналогична описанной в этом разделе для документов неучтенных продаж. На странице **Учтенный счет продажи** выберите действие **Журнал действий** для просмотра статуса электронного документа.  

## <a name="see-related-microsoft-trainingtrainingmoduleselectronic-documents-dynamics-365-business-centralindex" />См. соответствующее [обучение Microsoft](/training/modules/electronic-documents-dynamics-365-business-central/index)

## <a name="see-also" />См. также

[Выставление счетов продажи](sales-how-invoice-sales.md)  
[Настройка профилей отправки документов](sales-how-setup-document-send-profiles.md)  
[Настройка отправки и получения электронных документов](across-how-to-set-up-electronic-document-sending-and-receiving.md)  
[Настройка службы обмена документами](across-how-to-set-up-a-document-exchange-service.md)  
[Настройка определений обмена данными](across-how-to-set-up-data-exchange-definitions.md)  
[Электронный обмен данными](across-data-exchange.md)  
[Вопросы и ответы по электронным счетам](faq-electronic-invoicing.yml)  
[Общие бизнес-функции](ui-across-business-areas.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
