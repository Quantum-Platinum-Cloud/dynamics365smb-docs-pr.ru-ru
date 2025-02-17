---
title: Настройка оценки стоимости запасов и учета себестоимости
description: 'Чтобы обеспечить правильную запись валютных курсов, необходимо настроить различные поля и страницы, прежде чем приступать к выполнению товарных транзакций.'
author: SorenGP
ms.topic: conceptual
ms.search.keywords: null
ms.date: 06/16/2021
ms.author: edupont
---
# <a name="setting-up-inventory-valuation-and-costing" />Настройка оценки стоимости запасов и учета себестоимости

Чтобы обеспечить правильную запись валютных курсов, необходимо настроить различные поля и страницы, прежде чем приступать к выполнению товарных транзакций. Как правило, предприятия выбирают конкретный метод оценки себестоимости и применяют его к товарным запасам, например, чтобы помочь им отслеживать стоимость товаров на складе.  

> [!TIP]
> Введение по об оценке себестоимости [!INCLUDE [prod_short](includes/prod_short.md)] см. [Об оценке себестоимости товаров](finance-learn-about-costing.md).

В следующей таблице приводится последовательность задач со ссылками на разделы, в которых они описываются.

|**Задача**|**Раздел**|  
|------------|-------------|
|Укажите метод учета себестоимости по умолчанию для каждой компании для управления использованием входящей себестоимости с целью доступа к стоимости запасов и проданных товаров.|[Настройка общей информации по запасам](inventory-how-setup-general.md)|  
|Укажите метод оценки себестоимости для отдельных позиций, если для них требуется другой метод оценки себестоимости.|[Регистрация новых товаров](inventory-how-register-new-items.md)|  
|Обеспечение автоматического учета стоимости в главной книге при учете транзакции запасов.|Поле **Автомат. учет себест.** на странице **Настройка модуля "Запасы"**|  
|Обеспечение учета ожидаемой себестоимости в главной книге для определения по промежуточным счетам главной книги подлежащих оплате сумм и стоимости проданных товаров до фактического выставления за них счетов.|Поле **Учет ожидаемой себест. в ГК** на странице **Настройка модуля "Запасы"**|  
|Настройка системы для автоматической коррекции при любых изменениях себестоимости при каждом учете транзакции запасов.|[Корректировка себестоимости товаров](inventory-how-adjust-item-costs.md)|  
|Указание способа вычисления средней себестоимости: только для каждого товара или для каждого товара каждой единицы учета запасов и для каждой разновидности товаров.|Поле **Тип расчета средней себестоимости** на странице **Настройка модуля "Запасы"**|  
|Выбор периода времени, который приложение будет использовать для вычисления средневзвешенной себестоимости товаров, для которых используется метод средней себестоимости.|Поле **Период расчета средней себестоимости** на странице **Настройка модуля "Запасы"**|  
|Определение периодов учета запасов для управления стоимостью запасов во времени путем запрета учета транзакций в закрытых периодах учета запасов.|[Работа с учетными периодами](finance-how-to-work-with-inventory-periods.md)|  
|Обеспечение применения возврата продажи к исходной исходящей транзакции для сохранения стоимости запасов.|Поле **Точный возврат себест. обязат.** на странице **Продажи и расчеты с дебиторами**|  
|Обеспечение применения возврата покупок к исходной входящей транзакции для сохранения стоимости запасов.|Поле **Точный возврат себест. обязат.** на странице **Покупки и расчеты с кредиторами**|
|Настройка правил округления для применения при коррекции или предложении цен товаров и при корректировке или предложении стандартной себестоимости.|Страница **Метод округления**|  

## <a name="see-also" />См. также

[Управление себестоимостью товаров](finance-manage-inventory-costs.md)  
[Настройка общей информации по запасам](inventory-how-setup-general.md)  
[Выверка себестоимости товаров с главной книгой](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Рекомендации по настройке. Метод учета себестоимости](setup-best-practices-costing-method.md)  
[Сведения о проектировании: себестоимость запасов](design-details-inventory-costing.md)  
[Сведения о проектировании: изменение методов учета себестоимости для товаров](design-details-changing-costing-methods.md)  
[Работа с Business Central](ui-work-product.md)  
[Финансы](finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
