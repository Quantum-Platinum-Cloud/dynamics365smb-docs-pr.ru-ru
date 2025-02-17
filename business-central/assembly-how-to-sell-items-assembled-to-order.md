---
title: 'Продажа товара, собранного на заказ'
description: 'Узнайте, как продать товар, собранный на заказ.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 11/23/2022
ms.search.keywords: 'kit, kitting, substitute items'
ms.search.form: '900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905'
ms.custom: bap-template
---
# <a name="sell-items-assembled-to-order" />Продажа товара, собранного на заказ

Если товары настроены для сборки на заказ, их наличие на складе не ожидается, и эти товары будут быть собраны при их добавлении в заказ на продажу. Товар настраивается для сборки на заказ, если в поле **Политика сборки** на карточке товара указано **Сборка для заказа**. При вводе товара в строке заказа продажи автоматически создается заказ на сборку и связывается с заказом на продажу.  

> [!NOTE]  
> Если товары сборки для заказа уже находятся на складе, можно вычитать это количество из заказа на сборку и зарезервировать его со склада. Подробнее см. в разделе [Продажа складских товаров в потоках сборки для заказа](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

В рамках этой процедуры обрабатывается продажа товара, который будет собран в соответствии с спецификациями, которые запрошены клиентом. Эти шаги включают: 

* Создание строки заказа на продажу.
* Настройка сборочного элемента путем редактирования его компонентов и ресурсов.
* Проверка наличия для определения даты доставки.
* Выпуск заказа на продажу для сборки и немедленной отправки.  

> [!NOTE]  
> Следующая процедура не включает шаги по созданию стандартного заказа на продажу, происходящие до шага, на котором указывается товар сборки для заказа для строки заказа на продажу. Узнайте больше о создании заказов на продажу в разделе [Продажа товара с заказом продажи клиента](sales-how-sell-products.md).  

## <a name="to-sell-an-item-that-is-assembled-to-order" />Продажа товара, собранного на заказ

1. Выберите значок ![Лампочка, которая открывает функцию «Что вы хотите сделать»](media/ui-search/search_small.png "Что вы хотите сделать"), значок введите **Заказы на продажу**, а затем выберите связанную ссылку.  
2. Создайте заказ на продажу. 
3. В поле **Номер** введите товар, который настроен для сборки на заказ.  
4. В поле **Код склада** укажите, с какого склада должен быть продан товар. Процесс сборки будет выполняться на этом складе.  
5. В поле **Количество** укажите, сколько единиц будет продано.  

    > [!NOTE]  
    >  Если один или несколько компонентов запрошенного количества сборочных элементов недоступны, откроется страница предупреждения о доступности. <!-- Check whether the field help would be useful. For more information, see Assembly Availability.  -->

    Заказ на сборку создается и привязывается к строке заказа на продажу. Сроком выполнения заказа на сборку является дата отгрузки в строке заказа на продажу.  

    Количество, подлежащее продаже, копируется в поле **Количество для сборки на заказ**, в котором отражается, что для настройки товара требуется полное количество в товара в строке продажи, которое необходимо собрать для заказа. Можно сокращать количество для сборки, например, если известно, что некоторые товары уже доступны. Подробнее см. в разделе [Продажа складских товаров в потоках сборки для заказа](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

6. Если клиенту нужен дополнительный товар в комплекте, на экспресс-вкладке **Строки** выберите действие **Строка**, выберите действие **Сборка для заказа**, затем выберите действие **Строки сборки для заказа** для просмотра и изменения стандартных сборочных компонентов. В качестве альтернативы выберите поле **Количество для сборки на заказ**.  
7. На странице **Строки сборки для заказа** создайте новую строку типа **Товар** для дополнительного компонента сборки.  

    Можно также настроить заказ путем увеличения количества одного стандартного товара в комплекте. Для этого можно увеличить значение в поле **Кол-во в** конкретной строки сборочного заказа.  

    > [!NOTE]  
    >  Страница **Строки сборки для заказа** содержит только основные поля для настройки списка компонентов, добавления номеров трассировки товаров или для решения проблем с наличием компонентов. Чтобы добавить дополнительные сведения по заказу на сборку, в частности, дату начала заказа на сборку, выберите действие **Показать документы**. При этом откроется полное отображение сборочного заказа, связанного со строкой заказа продажи. Содержимое большинства полей в заголовке заказа на сборку невозможно изменить и учесть в выходе при сборке. Для этого требуется выполнить учет отгрузки из строки заказа на продажу.  
    >
    >  В связанных заказах на сборку можно изменить только поле **Дата начала**. Изменение даты начала позволяет сборщикам указать, что они начинают сборку раньше установленного срока. Все поля в строках связанного сборочного заказа можно изменить так, чтобы работники склада могли в процессе вводить цифры потребления.  

8. Просмотрите проблемы доступности компонентов или примите соответствующие меры. Например, выберите замещающий товар.  
9. Закройте страницу **Строки сборки на заказ**. Связанный заказ на сборку готов и рабочие могут начать сборку заказных товаров.  
10. В заказе на продажу выберите действие **Выпустить**, чтобы уведомить сборочный участок, что процесс сборки может быть запущен. Подробнее см. в разделе [Сборка товаров](assembly-how-to-assemble-items.md).  

> [!NOTE]  
> Замены товаров не заменяют автоматически товары другими товарами, например, при создании заказа на продажу или в спецификации. Вместо этого вы будете предупреждены о том, что вам доступна замена.

## <a name="see-related-microsoft-trainingtrainingmodulesassemble-to-order-dynamics-365-business-central" />См. соответствующее [обучение Microsoft](/training/modules/assemble-to-order-dynamics-365-business-central/)

## <a name="see-also" />См. также

[Управление сборкой](assembly-assemble-items.md)  
[Работа со сборочными спецификациями](assembly-how-work-assembly-boms.md)  
[Регистрация новых товаров](inventory-how-register-new-items.md)  
[Запасы](inventory-manage-inventory.md)  
[Обзор Warehouse Management](design-details-warehouse-management.md)
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
