---
title: Несколько контрактов | Документация Майкрософт
description: 'В соответствии с заключенными с клиентом соглашениями об уровне обслуживания может возникнуть необходимость работы с сервисным товаром, входящим в несколько сервисных контрактов.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="multiple-contracts" />Несколько контрактов
В соответствии с заключенными с клиентом соглашениями об уровне обслуживания может возникнуть необходимость работы с сервисным товаром, входящим в несколько сервисных контрактов.  
  
При работе с сервисным товаром под несколькими контрактами можно сделать следующее:  
  
* Создание различных контрактов для одного и того же сервисного товара.  
* Обслуживать части независимо друг от друга.  
* Рассматривать отдельные навыки, требуемые для обслуживания различных аспектов сервисного товара, таких как механические компоненты и программное обеспечение.  
* Укажите разное время отклика и частоту при обслуживании различных частей сервисного товара.  
* Осуществлять различные виды работ по отношению к сервисному товару, если этому товару требуются разные типы обслуживания в разные периоды времени.  
* Выберите и припишите строке сервисного товара подходящий номер контракта при создании сервисного заказа.  
* Работа с финансовой информацией, касающейся сервисных товаров и договоров об уровне обслуживания.  
  
Вот несколько примеров использования функциональных возможностей нескольких контрактов.  
  
## <a name="creating-multiple-contracts-per-service-item" />Создание нескольких контрактов для одного сервисного товара
Можно вручную создать сервисный контракт или предложение по контракту для сервисных товаров, уже зарегистрированных в других не отмененных контрактах того же клиента. Для этого достаточно выполнить стандартную процедуру создания сервисного контракта или предложения по контракту. Дополнительные сведения см. в разделе [Работа с сервисными контрактами и предложениями по сервисному контракту](service-how-to-create-service-contracts-and-service-contract-quotes.md).  
  
При добавлении в строку контракта сервисного товара, который уже зарегистрирован в другом сервисном контракте или предложении по контракту, на экран выводится предупреждение о том, что данный сервисный товар уже принадлежит одному или нескольким сервисным контрактам или предложениям по контракту. Если ответить на предупреждение утвердительно, вся относящаяся к данному сервисному товару информация будет скопирована в только что созданную строку контракта.  
  
## <a name="copying-documents" />Копирование документов
Можно автоматически создать сервисный контракт или предложение по контракту для сервисных товаров, уже зарегистрированных в других сервисных контрактах или сервисных предложениях, с помощью действия **Копировать из документа**.  
  
## <a name="creating-service-orders-for-multiple-contracts" />Создание сервисных заказов для нескольких контрактов
Можно вручную создать сервисный заказ для сервисного товара, зарегистрированного в нескольких активных контрактах. Сервисный контракт считается активным, когда он подписан и не просрочен.  
  
## <a name="see-also" />См. также
[Выполнение контрактов на обслуживание](service-fulfill-service-contracts.md)  
[Создание сервисных заказов](service-how-to-create-service-orders.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
