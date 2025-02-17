---
title: Обзор задач по распределению затрат и дохода
description: Описание задач по распределению операции финансового журнала по нескольким разным счетам при учете журнала.
author: SorenGP
ms.topic: overview
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '283, 5629'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="allocate-costs-and-income" />Распределить затраты и доход

При учете журнала операцию финансового журнала можно распределить по нескольким разным счетам. Для распределения можно воспользоваться тремя методами:

* количество;
* процент (%);
* Сумма

Функция распределения может использоваться с типовыми финансовыми журналами и в журналах основных средств.
<!--You can also distribute the cost or revenue of a line to an intercompany partner when you post a sales or purchase document. When you post the document, a line will be posted in your general journal, and a corresponding line will be created in the intercompany outbox.-->

Далее описана процедура подготовки к распределению затрат в типовом финансовом журнале путем определения ключей распределения. После определения ключей распределения вы выполняете и учитываете журнал как любой другой типовой финансовый журнал. Дополнительные сведения прочитайте в разделе [Работа с финансовыми журналами](ui-work-general-journals.md).

## <a name="to-set-up-allocation-keys" />Настройка ключей распределения

При учете журнала операцию типового финансового журнала можно распределить по нескольким разным счетам. Распределение может выполняться по количеству, по процентному отношению или сумме.  

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Типовой финансовый журнал**, а затем выберите связанную ссылку.
2. Выберите поле **Код раздела**, чтобы открыть страницу **Разделы финансового журнала**.
3. Вы можете изменить распределения в существующем разделе в списке или создать новый раздел с распределениями.
   * Для создания нового раздела выберите действие **Создать** и перейдите к следующему шагу.
   * Для изменения распределений в существующем журнале выберите журнал и перейдите к шагу 7.    
4. В поле **Название** укажите название раздела, например CLEANING. В поле **Описание** введите описание, например "Журнал для расходов по уборке".
5. По завершении закройте страницу. Откроется новый пустой типовой журнал.
6. Заполните поля строки.
7. Выберите действие **Распределения**.
8. Добавьте строку для каждого распределения. Следует по выбору заполнить поля **Распределение (%)**, **Распред. кол-во** или **Сумма**. Следует также заполнить поле **Номер счета** и, если производится распределение транзакции по глобальным измерениям, поля глобального измерения.
9. Если в строке указан процент, сумма в поле **Сумма** будет рассчитана автоматически. Эти суммы по знаку противоположны итоговой сумме из поля **Сумма** типового журнала.
10. После ввода строк распределения выберите **OK**, чтобы вернуться на страницу **Типовой финансовый журнал**. Поле **Распред. сумма (руб.)** будет заполнено и его значение будет соответствовать полю **Сумма**.
11. Выполните учет журнала.

## <a name="to-change-an-allocation-key-that-has-already-been-set-up" />Изменение уже настроенного ключа распределения
1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Типовой финансовый журнал**, а затем выберите связанную ссылку.
2. На странице **Типовой финансовый журнал** выберите журнал с распределением.
3. Выберите строку с распределением, а затем выберите действие **Распределения**.
4. Измените соответствующие поля и нажмите кнопку **ОК**.

## <a name="see-also" />См. также
[Закрытие года и периодов](year-close-years-periods.md)  
[Работа с финансовыми журналами](ui-work-general-journals.md)    
[Учет документов и журналов](ui-post-documents-journals.md)    
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
