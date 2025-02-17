---
title: Добавьте компании в свой раздел организации
description: 'Узнайте, как добавить компании из других сред Business Central в свой раздел организации, чтобы вы могли управлять работой в разных средах.'
author: edupont04
ms.topic: conceptual
ms.search.keywords: 'accountant, accounting, company hub'
ms.search.form: '1151, 1155, 1166, 1165'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="add-companies-to-your-company-hub" />Добавьте компании в свой раздел организации

С помощью раздела организации вы можете получить доступ к своей работе из нескольких компаний из нескольких сред [!INCLUDE [prod_short](includes/prod_short.md)]. Вы можете добавить среды и компании вручную, если ваши компании не отображаются автоматически в разделе организации.  

Прямо на целевой странице раздела организации вы найдете меню **Настройка**, откуда вы можете получить доступ на страницу **Ссылки на среды**. Просто нажмите **Создать**, а затем заполните соответствующие поля. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

> [!NOTE]
> Вы можете подключить к корпоративному узлу столько компаний, сколько вам нужно. Однако вы можете подключить узел компании только к компаниям, которые размещены в [!INCLUDE [prod_short](includes/prod_short.md)] Online.

## <a name="environment-links" />Ссылки на среды

Ссылка на среду — это карточка, на которой вы указываете среду [!INCLUDE [prod_short](includes/prod_short.md)], в которой размещается одна или несколько компаний, в которых вы работаете. Данные в карточке для каждой среды задаются вами, и вы можете изменять их при необходимости. Однако поле **Ссылка на среду** является критическим. С его помощью вы получаете доступ к каждой компании [!INCLUDE [prod_short](includes/prod_short.md)]. Воспользуйтесь действием **Проверить подключение** на ленте, чтобы убедиться, что вы указали правильную ссылку. Ссылка, которую вы должны ввести, указывает на среду, в которой размещается добавляемая вами компания, и должна включать Azure Active Directory (Azure AD) код или доменное имя организации. Например, если клиент указал домен MyBusiness.com, то ссылка на их [!INCLUDE [prod_short](includes/prod_short.md)] будет иметь вид ```https://businesscentral.dynamics.com/mybusiness.com?redirectedfromsignup=1```. В противном случае это будет выглядеть примерно так: ```https://businesscentral.dynamics.com/1a23b456-789c-0123-45de-678910fg12h/production?redirectedfromsignup=1```  

Ссылка используется при выборе компании в разделе организации.  

:::image type="content" source="media/company-hub-company-list-actions.png" alt-text="Действия для компании, которая указана в разделе организации.":::

> [!TIP]
> Если вы работаете в бесплатной пробной версии [!INCLUDE [prod_short](includes/prod_short.md)], легко добавить компании в ваш клиент. Ссылку на среду можно найти, скопировав код Azure Active Directory из раздела **Исправление проблем** на странице справки и поддержки. Имя среды, вероятно, является значением по умолчанию, PRODUCTION. Добавьте эту информацию в поле **Ссылка на среду**, например ```https://businesscentral.dynamics.com/1a23b456-789c-0123-45de-678910fg12h/production?redirectedfromsignup=1```, а затем выберите **Проверить подключение**. Оценочная компания будет добавлена в список.
>
> Если вы перешли в компанию "My Company" с тридцатидневной пробной версией, вы можете добавить ее в список, выбрав действие **Перезагрузить/перезагрузить все компании** в списке.

## <a name="load-companies" />Загрузка компаний

Когда вы добавите свои среды, ваши компании появятся автоматически. Однако, если вы знаете, что в среду была добавлена новая компания, вы можете выбрать действие **Перезагрузить все компании** для обновления списка. Используйте одно и то же действие для обновления данных по всем вашим компаниям.  

> [!TIP]
> Чтобы обновить данные в раздел организации, у вас должен быть доступ к данным в компаниях, из которых они поступают.

## <a name="see-also" />См. также

[Управление работой нескольких компаний в разделе организаций](company-hub.md)  
[Ресурсы для справки и поддержки](product-help-and-support.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
