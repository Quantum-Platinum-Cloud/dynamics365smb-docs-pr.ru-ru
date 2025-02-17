---
title: Настройка и обработка операции субподряда
description: 'Пошаговое руководство, чтобы узнать, как настроить и обработать операцию субподряда в Business Central.'
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# <a name="set-up-and-process-a-subcontracting-operation" />Настройка и обработка операции субподряда

В этой статье мы покажем вам, как использовать демонстрационные данные Contoso Coffee при субподряде.

## <a name="scenario" />Сценарий

Вы являетесь планировщиком производства в Contoso Coffee. Из-за нехватки производственных мощностей вы планируете использовать субподрядчика для производства товара **SP-SCM1009, Airpot**.

Здесь вы создаете новый выпущенный производственный заказ на 12 единиц товара SP-SCM1009, Airpot, используя маршрут — SP-SCM1009-SUB-2. Используйте лист субподряда, чтобы создать заказ на покупку для производства, а затем завершите операцию, получив заказ на покупку и выставив счет.

## <a name="steps" />Шаги

1. Создайте новый выпущенный производственный заказ на 12 единиц товара SP-SCM1009, Airpot.

    1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](../../media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Запущенный производственный заказ**, а затем выберите связанную ссылку.  

    2. Выберите действие **Создать**, затем заполните поля, как описано в следующей таблице.  

        |Поле  |Значение  |
        |---------|---------|
        |**Тип источника** |Товар|
        |**Номер источника** |SP-SCM1009|
        |**количество;** |100|
    3. Выберите действие **Обновление произв. заказа**.  

2. Замените маршрут на SP-SCM1009-SUB-2 в строке производственного заказа, а затем обновите производственный заказ, но только для маршрута.  

    1. Добавьте поле «Номер производственного маршрута» в «Строки» в выпущенном производственном заказе.<!--in code, this is marked as visible=false-->

    2. Измените поле **Номер маршрута** с *SP-SCM1009-SERIAL* на *SP-SCM1009-SUB-2*.  

    3. Выберите действие **Обновление произв. заказа**.  

    4. На странице запроса **Обновить производственный заказ** очистите поле **Строки** и **Требуемый компонент**, чтобы задача выполнялась только для маршрутизации, а затем выберите кнопку **ОК**.

3. Используйте лист субподряда, чтобы создать заказ на покупку для субподрядной операции в производственном заказе, созданном на шаге 2.  

    1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](../../media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Журнал субподрядов**, а затем выберите связанную ссылку.  

    2. Выберите действие **Расчет субподрядов**.

    3. Выберите поле **Принять указания** для новой строки.

    4. Выберите действие **Выполнить указание**.  

    5. На странице запроса **Выполнение указаний - заявка** примите все значения по умолчанию, а затем выберите кнопку **ОК**.

    6. Когда пакетное задание завершится, выберите кнопку **ОК**, чтобы закрыть лист субподряда.  

4. Получить и выставить счет на покупку.  

    1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](../../media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Заказы на покупку**, а затем выберите связанную ссылку.  

    2. В списке **Заказы на покупку** найдите заказ на покупку у поставщика 82000 Субподрядчик.

    3. В поле **Номер счета поставщика** введите *542349*.

    4. На экспресс-вкладке **Строки** выберите строку, а затем установите поле **Прямые затраты** как *18*.

    5. Выберите действие **Учет**.  

    6. В сообщении с запросом выберите параметр **Получить и выставить счет**.  

Вывод товара SP-SCM1009 Airpot теперь зарегистрирован.

## <a name="see-also" />См. также

[Введение в демонстрационные данные Contoso Coffee](../contoso-coffee-intro.md)  
