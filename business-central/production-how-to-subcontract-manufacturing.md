---
title: Субподрядное производство
description: 'В этом разделе дается расширенный обзор расширенных функциональных возможностей субподряда в Business Central, включая поля производственного центра и маршрутизацию.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 99000886
ms.date: 06/22/2021
ms.author: edupont
---
# <a name="subcontract-manufacturing" />Субподрядное производство

Передача определенных операций субподрядчику — это обычная практика во многих производственных организациях. Субподряд может быть редким событием или же может стать важной частью всех производственных процессов.

В [!INCLUDE[prod_short](includes/prod_short.md)] предусмотрено несколько инструментов управления субподрядными работами:  

- «Рабочие центры» с назначенным поставщиком: эта функция позволяет настраивать рабочий центр для одного поставщика (субподрядчика). Такой рабочий центр называется субподрядным. Можно указать субподрядный рабочий центр в операции маршрута, что позволяет легко управлять субподрядными операциями. Кроме того, себестоимость операции можно указывать на уровне маршрута или рабочего центра.  
- Себестоимость "Рабочего центра" на базе единиц или времени: эта функция позволяет указывать, будут ли расходы, связанные с рабочим центром, определяться на основе времени производства или фиксированной ставки за единицу. Хотя субподрядчики обычно применяют фиксированную ставку за единицу своих услуг, приложение поддерживает оба варианта (время производства и фиксированная ставка за единицу).  
- Журналы субподрядов: эта функция позволяет находить производственные заказы с материалами, готовыми к отправке субподрядчику, и автоматически создавать заказы на покупку для субподрядных операций из маршрутов производственных заказов. Приложение автоматически учитывает стоимость заказа на покупку в производственном заказе при учете заказа на покупку. С помощью журнала субподрядов можно просматривать и использовать только производственные заказы, имеющие статус запущенных.  

## <a name="subcontract-work-centers" />Субподрядные рабочие центры
«Субподрядные рабочие центры» настраиваются так же, как обычные рабочие центры с дополнительными данными. Они назначаются маршрутам таким же образом, как и прочие рабочие центры.  

### <a name="subcontract-work-center-fields" />Поля субподрядных рабочих центров
Поле **Код субподрядчика** позволяет обозначить рабочий центр как субподрядный. Можно ввести номер субподрядчика, снабжающего рабочий центр. Это поле может быть использовано для управления рабочими центрами, которые не находятся на предприятии, а работают по контракту.  

Если субподряд с поставщиком оформляется по разным ставкам для каждого процесса, установите флажок в поле **Специальная себест. единицы**. Это позволяет настраивать себестоимость по каждой строке маршрута и экономит время на повторный ввод данных для каждого заказа на покупку. При обработке используется себестоимость по строке маршрута, а не себестоимость по полям рабочего центра. Выбор поля **Специальная себест. единицы** позволяет вычислять себестоимость по поставщику для каждой операции маршрута.  

Если используется одна ставка для каждого субподрядчика, оставьте поле **Специальная себест. единицы** пустым. Себестоимость будет настраиваться путем заполнения полей **Прямая себестоимость единицы**, **Косвенные затраты (%)** и **Норма накладных расходов**.  

### <a name="routings-that-use-subcontract-work-centers" />Маршруты, использующие субподрядные рабочие центры
Субподрядные рабочие центры можно использовать для операций точно так же, как обычные рабочие центры.  

Можно настроить маршрут, использующий внешний рабочий центр, в качестве стандартного операционного шага. Другой вариант - изменить маршрут для конкретного производственного заказа, включив внешнюю операцию. Это может понадобиться в экстренной ситуации, например при неправильной работе сервера или при временном периоде повышенного спроса, когда работа, обычно выполняемая собственными силами, передается субподрядчику.  

Дополнительные сведения см. в разделе [Создание маршрутов](production-how-to-create-routings.md).  

## <a name="calculate-subcontracting-worksheets-and-create-subcontract-purchase-orders" />Вычисление листов субподрядов и создание заказов на покупку для субподряда
После расчета журнала субподряда создается соответствующий документ, в данном случае заказ на покупку.  

Страница **Журнал субподрядов** работает как **Журнал планирования**, вычисляя необходимую поставку, в данном случае — заказы на покупку, которые можно сначала просмотреть в журнале, а затем создать с помощью функции **Выполнить указание**.  

> [!NOTE]  
>  С помощью журнала субподрядов можно просматривать и использовать только производственные заказы со статусом **Выпущено**.  

### <a name="to-calculate-the-subcontracting-worksheet" />Вычисление листа субподряда
1.  Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Журнал субподрядов**, а затем выберите связанную ссылку.  
2.  Для расчета журнала выберите действие **Расчет субподрядов**.  
3.  На странице **Расчет субподрядов** задайте фильтры для субподрядных операций или для производственных центров, в которых они выполняются, чтобы вычислить только соответствующие производственные заказы.  
4.  Нажмите кнопку **ОК**.  

    Просмотрите строки на странице **Журнале субподрядов**. Данные в этот журнал поступают из строк производственного заказа и маршрута производственного заказа, и передаются в заказ на покупку при создании этого документа. Как и в случае с другими журналами, удаление строки в этом журнале не влияет на исходные данные. Информация появится снова при следующем использовании функции **Расчет субподрядов**.  

### <a name="to-create-the-subcontract-purchase-order" />Создание заказа на покупку для субподряда
1.  Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Журнал субподрядов**, а затем выберите связанную ссылку.  
2.  Выберите действие **Выполнить указание**.  
3.  Выберите поле **Печатать заказы**, чтобы распечатать заказ на покупку после его создания.  
4.  Нажмите кнопку **ОК**.  

Если все операции субподряда будут передаваться на один склад поставщика, создается только один заказ на покупку.  

Строка журнала, преобразованная в заказ на покупку, удаляется из журнала. После того как заказ на покупку создан, он не будет отображен в журнале повторно.  

## <a name="posting-subcontract-purchase-orders" />Учет субподрядных заказов на покупку
После создания субподрядных заказов на покупку их можно учитывать. При получении заказа операция из книги производственных мощностей учитывается в производственном заказе, а выставление счета по заказу учитывает прямые затраты заказа на покупку в производственном заказе.  

## <a name="to-post-a-subcontract-purchase-order" />Учет заказа на покупку по субподряду
1.  Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Заказы на покупку**, а затем выберите связанную ссылку.  
2.  Откройте заказ на покупку, созданный из журнала субподрядов.  

    В строках заказа покупки содержится та же информация, которая была в журнале. Поля **Номер производственного заказа**, **Номер строки произв. заказа**, **Номер произв. операции** и **Номер производственного центра** заполняются информацией из исходного производственного заказа.  

3.  Выберите действие **Учет**.  

Если покупка учитывается как полученная, выполняется автоматически учет операции журнала выхода для производственного заказа. Это справедливо, только если операция субподряда является последней операцией в маршруте производственного заказа.  

> [!CAUTION]  
>  Автоматически учет выхода будущих производственных заказов, когда получение субподрядных товаров не желательно. Причиной этого может быть то, что учтенное ожидаемое количество выпуска может отличаться от фактического количества и дата учета автоматической отгрузки может быть неверной.  
>   
>  Чтобы избежать учета результатов выполнения производственного заказа при получении покупок по субподряду, убедитесь, что операция субподряда не является последней. В качестве альтернативы вставьте новую последнюю операцию для окончательного количества выхода.  

Если заказ на покупку учитывается как заказ с выставленным счетом, прямая себестоимость заказа на покупку учитывается в производстве.  

## <a name="see-also" />См. также
[Производство](production-manage-manufacturing.md)    
[Настройка производства](production-configure-production-processes.md)  
[Планирование](production-planning.md)      
[Запасы](inventory-manage-inventory.md)  
[Покупки](purchasing-manage-purchasing.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
