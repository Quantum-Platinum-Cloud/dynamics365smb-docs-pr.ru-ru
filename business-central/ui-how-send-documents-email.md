---
title: Отправка документов и сообщений электронной почты
description: 'Вы можете определить содержимое для вставки в текст сообщения электронной, например ссылку на PayPal. Вы также можете вкладывать документы в сообщения электронной почты.'
author: edupont04
ms.topic: conceptual
ms.workload: na
ms.search.keywords: 'SMTP, mail, Microsoft 365, cover, body, PayPal, layout'
ms.search.form: null
ms.date: 04/01/2021
ms.author: edupont
---
# Отправка документов и сообщений электронной почты

Вы можете легко обмениваться информацией и документами, такими как заказы на продажу и покупку и счета-фактуры, по электронной почте прямо из [!INCLUDE[prod_short](includes/prod_short.md)], не открывая приложение электронной почты.  

Вы можете отправлять почти все типы документов в виде вложений PDF. Кроме того, вы можете настроить макет отчета, который включает информацию из документа в текст электронного письма вместе с текстом, который делает электронное письмо более дружелюбным, например, стандартное приветствие. Дополнительные сведения см. в разделе [Управление макетами отчетов и документов](ui-manage-report-layouts.md). <!--this topic does not mention how to set up a layout for email. Need to investigate.-->

Отправляя счета-фактуры, вы можете упростить клиентам выполнение платежей через платежную службу, например PayPal, путем автоматического добавления информации и ссылки на службу в электронное письмо. Дополнительные сведения см. в разделе [Включение платежей клиентов через службу платежей](sales-how-enable-payment-service-extensions.md).

Чтобы включить сообщения электронной почты в [!INCLUDE[prod_short](includes/prod_short.md)], запустите мастер настройки **Настройка электронной почты**. Дополнительные сведения см. в разделе [Настройка электронной почты](admin-how-setup-email.md).

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] поддерживает только исходящую электронную почту. Вы не можете также получать ответы в приложении.

## Отправка документов по электронной почте

Эта процедура описывает, как прикрепить учтенный счет-фактуру к электронному письму в виде файла PDF с текстом электронного письма для конкретного документа. <!--update this-->

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Учтенные счета продажи**, а затем выберите связанную ссылку.
2. Укажите счет, затем выберите действие **Печатать/Отправить** и выберите **Отправить**.
3. В поле **Эл. почта** выберите **Да (запросить настройки)**. Дополнительные сведения см. в разделе [Настройка профилей отправки документов](sales-how-setup-document-send-profiles.md).
    
    Если в поле **Эл. почта** страницы **Кому отправить документ** установлено значение **Да (запросить настройки)**, то откроется страница **Отправить сообщение эл. почты** с заполненным полем **Кому:** и документом, приложенным в виде PDF-файла. В поле **Содержание** вы можете либо ввести текст вручную или заполнить его настроенным текстом, связанным с типом документа.

4. Нажмите кнопку **ОК**.
5. В поле **Кому:** введите допустимый адрес электронной почты. Значение по умолчанию — адрес электронной почты клиента.
6. В поле **Тема** введите описательный текст темы. Значение по умолчанию — имя и номер счета клиента.
7. В поле **Вложение** созданный счет по умолчанию прикрепляется как PDF-файл.
8. В поле **Содержание** введите краткое сообщение получателю.

    Если на странице **Выбор отчета - продажи** настроен текст сообщения электронной почты, связанный с документом, поле **Содержание** заполняется автоматически. Для получения дополнительной информации см. раздел [Настройка повторно используемых текстов и макетов сообщений электронной почты](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts).
9. Нажмите кнопку **ОК** для отправки сообщения электронной почты.

> [!NOTE]  
> Если вам не нужно указывать параметры электронной почты при каждой отправке документа, вы можете выбрать вариант **Да (использовать настройки по умолчанию)** в поле **Эл. почта** на странице **Кому отправить документ**. В этом случае страница **Отправить сообщение эл. почты** открываться не будет. См. шаг 4. Дополнительные сведения см. в разделе [Настройка профилей отправки документов](sales-how-setup-document-send-profiles.md).  

## Составление и отправка сообщения электронной почты

Вы можете быстро составлять электронные письма для контактов, клиентов, поставщиков, продавцов/покупателей и банковских счетов прямо со страниц этих объектов. Просто выберите **Процесс**, а затем **Отправить электронное письмо**, чтобы открыть редактор электронной почты. Для банковских счетов действие **Отправить электронное письмо** находится в **Действия**.

> [!TIP]
> Если вы часто отправляете сообщения электронной почты, которые похожи по своей природе, или хотите отправить массовую рассылку, например, для рекламной кампании продаж, использование шаблонов Word с электронной почтой может ускорить процесс. Вы можете создать шаблон для таких объектов, как клиенты, поставщики и контакты, который будет генерировать содержимое электронного сообщения для вас и даже персонализировать содержимое для получателя на основе данных в [!INCLUDE[prod_short](includes/prod_short.md)]. Для получения дополнительной информации см. [Использование шаблонов Word для массовых сообщений](ui-mail-merge.md).  

Если вам назначен сценарий электронной почты, связанный с сущностью, которой вы отправляете электронное письмо, или документом, который вы отправляете, вложение может быть автоматически добавлено к вашему сообщению. Это связано с тем, что для сценария электронной почты было назначено вложение по умолчанию. Вы можете удалить вложение, если не хотите отправлять его вместе с сообщением. Для получения дополнительной информации см. раздел [Назначение сценариев электронной почты учетным записям электронной почты](admin-how-setup-email.md#assign-email-scenarios-to-email-accounts). 

## Документы, помеченные как распечатанные при отправке

Некоторые документы в [!INCLUDE[prod_short](includes/prod_short.md)] имеют поле, которое указывает, сколько раз этот документ был напечатан. Число в этом поле <!--"that field?" need a name...--> также обновляется, если вы отправляете документ по электронной почте, потому что для него создается файл PDF. Число обновляется, даже если вы не отправляете электронное письмо. <!--guessing this is because emails are technically reports, so the counter bumps up whenever someone creates an email. Need to verify.-->

## Отправленные сообщения электронной почты и ваш ящик "Исходящие"

[!INCLUDE[prod_short](includes/prod_short.md)] хранит сообщения электронной почты, которые вы отправляете, на странице **Отправленные**. Это позволяет вам повторно отправлять сообщения электронной почты или пересылать их кому-то другому. Если вы не можете найти сообщение электронной почты среди отправленных, поищите его на странице **Исходящая электронная почта**. 

> [!NOTE]
> В зависимости от расширения, которое ваша компания использует для электронной почты, администраторы могут видеть список сообщений, отправленных всеми, но не содержимое сообщений

В пункте **Исходящая электронная почта** вы найдете сообщения электронной почты, которые вы сохранили как черновики, и сообщения электронной почты, которые не удалось отправить, например, если адрес электронной почты был недействительным. Для сообщений, которые не удалось отправить, вы можете выбрать **Показать ошибку** или **Исследовать ошибку** для устранения проблемы.  

## См. соответствующее [обучение Microsoft](/training/modules/set-up-email/)

## См. также

[Управление макетами отчетов и документов](ui-manage-report-layouts.md)  
[Настройка электронной почты](admin-how-setup-email.md)  
[Выставление счетов продажи](sales-how-invoice-sales.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
