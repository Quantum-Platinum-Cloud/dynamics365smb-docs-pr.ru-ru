---
title: Использование Excel для импорта данных в Business Central
description: Используйте пакет конфигурации по умолчанию для добавления данных в Excel и импорта данных обратно в Business Central.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'migration, Excel'
ms.date: 05/10/2022
ms.author: edupont
---
# <a name="import-business-data-from-other-finance-systems" />Импорт бизнес-данных из других финансовых систем

При регистрации в [!INCLUDE[prod_short](includes/prod_short.md)] вы можете создать пустую организации, чтоб загрузить собственные данные и протестировать новую организацию [!INCLUDE[prod_short](includes/prod_short.md)]. В зависимости от финансового решения, которое вы используете сейчас, вы можете перенести информацию о клиентах, поставщиках, запасах и банковских счетах.  

Из ролевого центра вы можете запустить руководство по настройке, помогающее перенести бизнес-данные из файла Excel или из других форматов. Тип файлов, которые можно загружать, зависит от доступных расширений. Например, вы можете перенести данные из QuickBooks, поскольку [!INCLUDE[prod_short](includes/prod_short.md)] включает расширение, которое обрабатывает преобразование из QuickBooks. Если вам нужно перенести данные из других финансовых решений, вы должны проверить, есть ли расширение для этого решения, или импортировать из Excel.  

[!INCLUDE[prod_short](includes/prod_short.md)] включает шаблоны для счетов, клиентов, поставщиков и складских товаров, которые можно выбрать для применения при импорте данных. Для импорта изображений товаров можно использовать специальную функцию на странице **Настройка модуля "Запасы"**. Дополнительные сведения см. в разделе [Импорт нескольких изображений товаров](inventory-how-import-item-pictures.md).

> [!TIP]  
> Рекомендуется использовать мастеры миграции данных для импорта данных из Dynamics GP, Dynamics NAV или QuickBooks. Для получения дополнительной информации см. раздел [Перенос локальных данных в Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) в материалах для администраторов или [Перенос данных QuickBooks](ui-extensions-quickbooks-data-migration.md).

## <a name="work-with-data-in-excel" />Работа с данными в Excel

Вы можете использовать надстройку Excel для подготовки существующих данных к использованию в [!INCLUDE [prod_short](includes/prod_short.md)]. Дополнительную информацию см. в разделе [Просмотр и редактирование в Excel из Business Central](across-work-with-excel.md).  

## <a name="import-data-from-configuration-packages" />Импорт данных из пакетов конфигураций

Для внедрения больших объемов данных вы можете настроить пакеты конфигурации для конкретного решения. Дополнительные сведения см. в разделе [Настройка стандартных пакетов конфигурации компании](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages) в материалах для администраторов (только на английском языке).  

> [!NOTE]  
> Работа с пакетами конфигураций — расширенная функция, и рекомендуется связаться с партнером по перепродаже. Дополнительные сведения см. в разделе [Настройка стандартных пакетов конфигурации компании](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages) (только на английском языке).

Можно импортировать основные данные и некоторые транзакционные данные из других финансовых систем на основе пакета конфигурации по умолчанию в [!INCLUDE[prod_short](includes/prod_short.md)]. На странице **Пакеты конфигураций** можно использовать пакет для импорта и проверки данных перед применением пакета. Например, вы можете экспортировать пакет конфигурации в Excel, а затем настроить там данные. После этого можно импортировать данные обратно из Excel. Пакет состоит из 27 таблиц, включая основные данные, такие как клиенты, поставщики, товары и счета, другие таблицы настройки, такие как методы отгрузки, и таблицы транзакций, такие как заголовок и строки продаж.  

При экспорте пакета конфигурации по умолчанию в Excel созданная книга содержит лист для каждой таблицы в пакете. Чтобы упростить задачи, можно воспользоваться преимуществами инструментов управления XML, которые встроены в Excel. Также можно воспользоваться встроенными функциями Excel, чтобы помочь с форматом данных и поместить данные в правильную ячейку. Например, добавьте пустой лист и скопируйте в него устаревшие данные. Затем создайте формулу Excel для сопоставления данных в листе преобразования между полями в экспортированном листе и устаревшими данными клиента. После сопоставления всех данных скопируйте диапазон данных в табличный журнал.  

> [!IMPORTANT]  
> Не изменяйте столбцы в журналах. Если они перемещаются, изменяются или удаляются, то импортировать лист в [!INCLUDE[prod_short](includes/prod_short.md)] невозможно.

> [!NOTE]
> Поля типа Blob не могут быть экспортированы/импортированы с использованием Excel.

### <a name="tables-in-the-default-configuration-package" />Таблицы в пакете конфигурации по умолчанию

Пакет конфигурации по умолчанию поддерживает следующие таблицы:

- Условия оплаты
- Ценовая группа клиента
- Метод поставки
- Менеджер по продажам/закупкам
- Склады
- Счет ГК
- Клиент
- Поставщик
- Пункт меню
- Заголовок продажи
- Строка продажи
- Заголовок покупки
- Строка покупки
- Строка финансового журнала
- Строка журнала товаров
- Учетная группа клиента
- Учетная группа поставщика
- Учетная группа товаров
- Единица измерения
- Строка финансового бизнес-группа
- Строка финансового товарная группа
- Общая настройка учета
- Территория
- Категория товара
- Цена продажи
- Цена покупки

## <a name="see-also" />См. также

[Перенос локальных данных в Business Central Online (только на английском языке)](/dynamics365/business-central/dev-itpro/administration/migrate-data)  
[Настройка пакетов конфигурации организации](/dynamics365/business-central/dev-itpro/administration/set-up-standard-company-configuration-packages)  
[Миграция данных QuickBooks](ui-extensions-quickbooks-data-migration.md)  
[Импорт нескольких изображений товаров](inventory-how-import-item-pictures.md)

## <a name="includeprodshortincludesfreetrialmdmd" />[!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]
