---
title: Расширения облачной миграции
description: Используйте расширения облачной миграции для переноса локальных данных в сетевую версию Business Central. Эти расширения перемещают ваши локальные данные в облако.
author: jenolson
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'app, add-in, manifest, customize, import, implement'
ms.search.form: '4021, 4026, 4031, 4090, 4091, 4092, 4093, 4094, 4095, 4096, 4097, 40027,'
ms.reviewer: edupont
ms.date: 06/23/2021
ms.author: edupont
---

# <a name="cloud-migration-extensions-for-migrating-to-business-central-online" />Расширения облачной миграции для перехода на Business Central Online

В зависимости от вашего локального решения вы должны использовать разные расширения для подключения ваших данных к [!INCLUDE[prod_short](includes/prod_short.md)] Online с целью переноса вашего решения в облако.  

Если используется локальная версия одного из поддерживаемых продуктов, можно настроить среду облака на основе специального расширения для этого продукта. После настройки вашей среды облака можно будет перенести данные из вашего локального решения в [!INCLUDE[prod_short](includes/prod_short.md)]. Это позволит вам полностью использовать преимущества облака для вашего бизнеса, такие как улучшенный анализ бизнеса, искусственный интеллект, доступ с нескольких устройств и доступ в любой момент из любого места.  

Для получения дополнительной информации см. раздел [Миграция локальных данных в Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) в материалах для администраторов [!INCLUDE[prod_short](includes/prod_short.md)].  

## <a name="business-central-on-premises" />Локальная версия Business Central

Если используется локальное развертывание [!INCLUDE[prod_short](includes/prod_short.md)], получите расширения **Основа интеллектуального облака** и **Интеллектуальное облако Business Central**, затем выполните мастер настройки **Настройка миграции в облако**.  

## <a name="dynamics-gp" />Dynamics GP

Если используется Dynamics GP, получите расширения **Базовое расширение интеллектуального облака** и **Интеллектуальное облако Dynamics GP**, затем запустите мастер настройки **Настройка миграции в облако**.  

> [!IMPORTANT]
> Миграция из Dynamics GP с использованием мастер настройки **Настройка миграции в облако** в настоящее время поддерживается только для следующих рынков: США, Канада, Соединенное Королевство.

## <a name="dynamics-sl" />Dynamics SL

Если используется Dynamics SL, получите расширения **База интеллектуального облака**, **Интеллектуальное облако Microsoft Dynamics SL** и **Смарт-листы истории Microsoft Dynamics SL**, затем запустите мастер настройки **Настройка миграции в облако**.  

## <a name="see-also" />См. также

[Базовое расширение миграции в облако](ui-extensions-intelligent-cloud.md)  
[Миграция локальных данных в Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
