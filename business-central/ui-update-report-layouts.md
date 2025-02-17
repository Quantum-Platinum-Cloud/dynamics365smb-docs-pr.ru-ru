---
title: Обновление пользовательских макетов отчетов
description: 'Узнайте, как обновить настраиваемый макет отчета, используемый в отчете, например, при изменении дизайна набора данных отчета.'
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '9652, 9650'
ms.date: 06/24/2021
ms.author: edupont
---
# <a name="legacy-update-custom-report-layouts" />(Устарело) Обновление пользовательских макетов отчетов

[!INCLUDE[legacy-custom-layouts](includes/legacy-custom-layouts.md)]

Время от времени может возникать необходимость обновления пользовательского макета, который будет использоваться для отчета. Это необходимо при внесении изменений в конструкцию набора данных отчета, например если поле, используемое в макете, было удалено из набора данных отчета. Если макет отчета требует обновления, вы получите сообщение об ошибке при попытке просмотра, печати или сохранения отчета.  

Можно автоматически обновить макет отчета из сообщения об ошибке, которое отображается при выполнении отчета, выбрав кнопку **Да** в сообщении об ошибке. Можно также перед выполнением отчетов обновить отдельные макеты отчетов или все пользовательские макеты отчетов, на которые могут оказывать влияние изменения наборов данных.  

Кроме того, есть возможность проверить обновления без применения обязательных изменений для пользовательских макетов отчетов. Это позволяет понять, какие изменения будут применены к макету отчета, и выявить возможные проблемы, связанные с этим процессом. Из результатов проверки можно сразу открыть пользовательские макеты отчетов для редактирования и исправить ошибки. Рекомендуется проверить обновление макета отчетов перед применением обновлений.  

Не все изменения в наборах данных отчетов могут автоматически применяться для макетов отчетов. Для некоторых изменений потребуется вручную изменить макет отчета. Для получения дополнительных сведений см. раздел [Ограничения при обновлении пользовательского макета отчета](ui-update-report-layouts.md#UpdateLimitations).  

## <a name="to-update-one-or-more-custom-report-layouts" />Обновление одного или нескольких пользовательских макетов отчетов

1.  Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Выбор макета отчета**, а затем выберите связанную ссылку.  

2.  Если требуется обновить конкретный отчет, на странице **Выбор макета отчета** выберите макет из списка, затем выберите действие **Обновить макет**. Или, если требуется обносить все пользовательские макеты отчетов для организации, выберите действие **Обновить все макеты**.  

Если ошибок нет, обновления применяются к макетам отчетов. В случае возникновения ошибок выводится сообщение с их описанием. Затем потребуется вручную изменить пользовательский макет отчета, чтобы устранить ошибку. Для получения дополнительных сведений см. раздел [Исправление ошибок](ui-update-report-layouts.md#FixErrors).  

## <a name="to-test-custom-report-layout-updates" />Проверка обновлений пользовательских макетов отчетов

1.  Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Выбор макета отчета**, а затем выберите связанную ссылку.  

2.  На странице **Выбор макета отчета** выберите действие **Проверить обновления макетов**.  

 Изменения в макетах отчета проверяются, но не применяются к фактическим макетам отчетов. Откроется страница **Журнал обновлений макетов отчетов**, содержащее сведения о статусе потенциальных обновлений для каждого макета отчета. Если в макете отчета выявлены ошибки, можно перейти в него непосредственно из окна сообщения для редактирования и устранить ошибки. Для получения дополнительных сведений см. раздел [Исправление ошибок](ui-update-report-layouts.md#FixErrors).  

## <a name="a-nameupdatelimitationsa-limitations-of-the-custom-report-layout-update" /><a name="UpdateLimitations"></a> Ограничения при обновлении пользовательского макета отчета
 Существует несколько типов изменений, которые могут применяться при автоматическом обновлении к пользовательским макетам отчетов, например при удалении из набора данных отчета поля, которое использовалось в макете. Тем не менее, автоматическое обновление не может применить перечисленные ниже изменения в наборе данных отчета.  

1.  Удаленные поля, названия или элементы данных.  

2.  Дубликаты имен полей в макете отчета после переименования поля в наборе данных. Это считается ошибкой проектирования.  

3.  Сценарии обновления с несколькими циклами применения макета отчета, что ведет к нескольким переименованиям одних и тех же полей, названий или элементов данных.  

 Если в процессе обновления будет выявлена одна из таких проблем, обновление не применяется. Такие проблемы требуется исправить вручную, например, изменив макет отчета в Word либо программным способом с использованием модулей codeunit обновления.  

## <a name="a-namefixerrorsa-fixing-errors" /><a name="FixErrors"></a> Исправление ошибок
 В случае вывода сообщения об ошибке при обновлении или проверке обновлений макетов отчетов, скорее всего, возникнет необходимость изменить макет отчета для устранения этой проблемы. Прочитайте сообщения об ошибках, чтобы помочь определить причину проблемы.  

 Наиболее распространенная проблема происходит, если поле, используемое в макете, было удалено из набора данных отчета. В данном случае отобразится строка в сообщении об ошибке, где будет указано, что товар был удален. Для устранения этой проблемы потребуется изменить макет и удалить соответствующее поле.  

 Дополнительные сведения см. в разделе [Создание и изменение пользовательского макета отчета](ui-how-create-custom-report-layout.md#ModifyCustomLayout).  

После изменения макета попытайтесь обновить его снова.  

## <a name="see-related-microsoft-trainingtrainingmoduleschange-documents-dynamics-365-business-centralindex" />См. соответствующее [обучение Microsoft](/training/modules/change-documents-dynamics-365-business-central/index)

## <a name="see-also" />См. также
 [Управление макетами отчетов](ui-manage-report-layouts.md)  
 [Работа с отчетами, пакетными заданиями и XMLport](ui-work-report.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
