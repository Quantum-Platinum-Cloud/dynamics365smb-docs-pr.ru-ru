---
title: Расширение базового взаимодействия | Документы Microsoft
description: Это расширение является модернизированной альтернативой Microsoft Dynamics C5.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'C5, financials, extension'
ms.search.form: '20600,'
ms.date: 04/01/2021
ms.author: bholtorf
---

# <a name="the-basic-experience-extension" />Расширение базового взаимодействия

Если вы использовали Microsoft Dynamics C5, партнеры Майкрософт могут помочь вам перейти на более современное решение, основанное на [!INCLUDE[prod_short](includes/prod_short.md)], так что вы можете продолжать пользоваться теми же усовершенствованными возможностями, что и Dynamics C5.

Это расширение предназначено для малого бизнеса и может поддерживать до трех пользователей. Если вам нужно больше пользователей, вы должны перейти на лицензию [!INCLUDE[prod_short](includes/prod_short.md)] и удалить это расширение.

> [!NOTE]
> На данный момент это расширение доступно только клиентам в Дании и Исландии.

## <a name="whats-available" />Что доступно

В следующей таблице описаны возможности, которые доступны при установке расширения базового взаимодействия.

|С областями  |Функциональность  |
|---------|---------|
|**Главная книга** |Основные финансы, финансовые отчеты, основные средства, управление банком, выверка банковских счетов, платежи, прямой дебет, измерения, несколько валют, бюджеты, рабочий процесс, управление документами/OCR, консолидация, неограниченное количество компаний|
|**Дебиторская задолженность/продажи** |Базовая дебиторская задолженность, выставление счетов-фактур, скидки с продаж, цены, налог с продаж, управление контактами |
|**Кредиторская задолженность/покупка** |Основная кредиторская задолженность, выставление счетов за закупку |
|**Управление проектами** |Вакансии, расценки на вакансии, табели учета рабочего времени, задания, задачи, ресурсы |
|**Наличие** |Базовые запасы, замена товаров, перекрестная ссылка на товары |

## <a name="getting-started" />Приступая к работе

Это расширение немного отличается от большинства, и вам потребуется помощь партнера Microsoft для его установки и настройки. Чтобы вы знали, чего ожидать, вот общее представление о том, что будет делать партнер Microsoft.

1. Создание нового клиента [!INCLUDE[prod_short](includes/prod_short.md)]. Это может быть пробная версия или версия поставщика облачных решений (CSP).
2. Добавьте хотя бы одного пользователя, которому назначена лицензия базового взаимодействия в вашей учетной записи Azure Active Directory.
3. Удалите все компании, включая образец компании Cronus.
4. Создайте новую компанию, которая не содержит никаких примеров данных или настроек.
5. Добавьте пакет **Демонстрация RapidStart**. <!--what does the package contain?-->
6. Загрузите и установите расширение базового взаимодействия из AppSource.

## <a name="migrating-data" />Миграция данных

Возьмите с собой данные Dynamics C5. После того, как ваш партнер Microsoft установит расширение базового взаимодействия, у вас будет пустая компания. Простой способ перенести данные из Dynamics C5 в базовое взаимодействие — использовать расширение C5 Data Migration, которое включено в [!INCLUDE[prod_short](includes/prod_short.md)]. Расширение переносит клиентов, поставщиков, товары, а также ваши счета главной книги и их записи.

## <a name="see-also" />См. также

[Расширение миграции данных C5](ui-extensions-c5-data-migration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
