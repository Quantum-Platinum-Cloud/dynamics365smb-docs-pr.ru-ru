---
title: Создание содержимого ячейки
description: 'После того, как вы настроили свои корзины, вы можете указать товары, которые вы хотите хранить в них, и настроить правила, которые контролируют частоту пополнения корзин.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 7374
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="create-bin-contents" />Создание содержимого ячейки

После настройки ячеек можно настроить содержимое ячеек. Другими словами, можно задавать товары, которые предполагается хранить в каждой конкретной ячейке, и правила заполнения ячейки конкретным товаром. Это можно сделать вручную на странице **Содержимое ячейки** или автоматически с помощью страницы **Создание журнала содержимого ячейки**.

## <a name="to-create-bin-content-manually" />Создания содержимого ячейки вручную

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Склады**, а затем выберите связанную ссылку.  
2. Выберите склад, где необходимо настроить содержимое ячейки, затем выберите действие **Ячейки**.  
3. Выберите ячейку, где необходимо настроить содержимое, затем выберите действие **Содержимое**.  
4. Для каждого товара, подлежащего хранению в ячейке, заполните строку на странице **Содержимое ячейки** соответствующей информацией. Некоторые поля предварительно заполняются информацией о ячейке.  
5. Сначала заполните поле **Код товара**, затем, если используется расширенный подбор и размещение, заполните поля **Код единицы измерения**, **Макс. кол-во** и **Мин. кол-во**.  

При необходимости выберите поле **Фиксированный**. Если ячейка должна использоваться в качестве стандартной ячейки товара, выберите поле **Стандартная ячейка**.  

Если используется расширенный подбор и размещение, и в карточке товара введена правильная информация о единицах измерения габаритов товара, будет проверено соответствие максимального количества, введенного на странице **Содержимое ячейки**, физической емкости ячейки. Минимальное и максимальное количество используются при расчете возобновления ячеек и предлагаемых размещений.  

Если выбрано поле **Фиксир.**, товар фиксируется для ячейки, что означает, что [!INCLUDE[prod_short](includes/prod_short.md)] попытается разместить товар в ячейке, если для него есть место, и сохранит запись фиксации товара к ячейке даже в том случае, если количество в ячейке равно нулю. Другие товары могут быть размещены в ячейке, даже если определенный товар был для нее зафиксирован.  

> [!NOTE]  
> На странице **Журнале создания содержимого ячеек** можно одновременно настраивать содержимое для нескольких ячеек.  

## <a name="to-create-bin-content-with-a-worksheet" />Создание содержимого ячейки с помощью журнала

После создания ячеек можно создать желаемое содержимое ячеек в журнале содержимого ячеек.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](media/ui-search/search_small.png "Что вы хотите сделать") введите **Журнал создания содержимого ячеек**, а затем выберите связанную ссылку.  
2. В заголовке журнала в поле **Название** выберите журнал склада, в котором необходимо создать содержимое ячеек.  
3. В поле **Код ячейки** выберите код ячейки, для которой требуется определить содержимое.  

    Если на этом складе используется расширенный подбор и размещение, то поля, относящиеся к этой конкретной ячейке поля, например **Тип ячейки**, **Склад - код класса** и **Рейтинг ячейки**, заполняются автоматически. Эту информацию необходимо принимать во внимание при определении содержимого ячейки.  
4. Выберите товар, который будет закреплен за ячейкой, и заполните поля, относящиеся к содержимому ячейки. Если используется расширенное размещение и подбор и требуется воспользоваться функцией **Расчет пополнения ячеек**, заполните поля **Макс. кол-во** и **Мин. кол-во**.  

    Чтобы настроить эту ячейку как предпочитаемую ячейку для товара, даже если количество товара в ячейке равно **0** (все остальные критерии размещения равны), выберите поле **Фиксированный**.  
5. Повторите шаги с 3 по 4 для каждого товара, который нужно назначить ячейке.  
6. Выберите действие **Печать**, чтобы просмотреть и распечатать содержимое ячейки, введенное в журнал. Продолжайте изменять содержимое ячейки, пока оно не будет соответствовать всем требованиям.  
7. Когда будете готовы, выберите действие **Создать содержимое ячеек**.  

В данном журнале вы работаете с несколькими строками содержимого ячейки для нескольких ячеек и, следовательно, получаете хороший обзор того, что помещается в различные ячейки в данной зоне, пролете или ряду.  

## <a name="see-related-microsoft-trainingtrainingmodulesset-up-zones-bins" />См. соответствующее [обучение Microsoft](/training/modules/set-up-zones-bins/)

## <a name="see-also" />См. также

[Обзор управления складом](design-details-warehouse-management.md)
[Запас](inventory-manage-inventory.md)  
[Настройка управления складом](warehouse-setup-warehouse.md)  
[Управление сборкой](assembly-assemble-items.md)  
[Работа с [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
