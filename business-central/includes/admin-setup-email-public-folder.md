---
author: edupont04
ms.topic: include
ms.date: 02/15/2022
ms.author: edupont
---

> [!NOTE]
> В следующих разделах предполагается, что у вас есть права администратора для Exchange Online.

Прежде чем вы сможете настроить регистрацию электронной почты, вы должны подготовить [общие папки](/exchange/collaboration-exo/public-folders/public-folders) Office 365. Вы можете сделать это в [центре администрирования Exchange](/exchange/exchange-admin-center?preserve-view=true) или вы можете использовать [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps&?preserve-view=true).

> [!TIP]
> Если вы хотите использовать [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps&preserve-view=true), Вы можете найти вдохновение для того, как настроить свой скрипт в примере скрипта, который мы опубликовали в [репозитории BCTech](https://github.com/microsoft/BCTech/tree/master/samples/EmailLogging).

Следуйте инструкциям ниже, чтобы настроить Exchange Online, со ссылками на то, где можно узнать больше.

### <a name="create-an-admin-role-group" />Создайте группу ролей администратора

Создайте группу ролей администратора для общих папок на основе информации в следующей таблице:

|Свойство        |Значение                     |
|----------------|--------------------------|
|Name            |Управление общими папками |
|Избранные роли  |Общие папки            |
|Выбранные пользователи  |Электронный адрес учетной записи пользователя, которую Business Central будет использовать для выполнения задания регистрации электронной почты.|

Дополнительные сведения см. в разделе [Управление группами ролей в Exchange Online](/exchange/permissions-exo/role-groups).

### <a name="create-a-new-public-folder-mailbox" />Создать новый почтовый ящик общедоступной папки

Создайте новый почтовый ящик для общих папок на основе информации в следующей таблице:

|Свойство        |Значение                     |
|----------------|--------------------------|
|Name            |Общий почтовый ящик            |

Дополнительные сведения см. в разделе [Создание нового почтового ящика для общих папок](/exchange/collaboration-exo/public-folders/create-public-folder-mailbox).

### <a name="create-new-public-folders" />Создание новых общих папок

1. Создайте новую общую папку с именем **Регистрация электронной почты** в корне, чтобы полный путь к папке стал `\Email Logging\`.
2. Создайте две подпапки, чтобы в результате были получены следующие полные пути к папкам:

    - `\Email Logging\Queue\`
    - `\Email Logging\Storage\`

Дополнительные сведения см. в разделе [Создание общей папки](/exchange/collaboration-exo/public-folders/create-public-folder).

### <a name="set-public-folder-ownership" />Установить право собственности на общую папку

Установите пользователя регистрации электронной почты как владельца обеих общих папок, *Очередь* и *Хранение*.

Дополнительные сведения см. в разделе [Назначение разрешений для общей папки](/exchange/collaboration-exo/public-folders/set-up-public-folders#step-3-assign-permissions-to-the-public-folder).

### <a name="mail-enable-the-queue-public-folder" />Включение поддержки электронной почты для общая папка *Очередь*

  Дополнительные сведения см. в разделе [Включение или отключение поддержки электронной почты для общей папки](/exchange/collaboration-exo/public-folders/enable-or-disable-mail-for-public-folder).

### <a name="mail-enable-sending-emails-to-the-queue-public-folder" />Оправка электронной почты с включением почты в общую папку *Очередь*

Включение поддержки электронной почты отправка сообщений электронной почты в общая папка *Очередь* с помощью Outlook или Командная консоль Exchange.

Дополнительные сведения см. в [Разрешить анонимным пользователям отправлять сообщения электронной почты в общую папку с включенной поддержкой электронной почты](/exchange/collaboration-exo/public-folders/enable-or-disable-mail-for-public-folder#allow-anonymous-users-to-send-email-to-a-mail-enabled-public-folder?preserve-view=true).

### <a name="create-mail-flow-rules" />Создать правила потока почты

Создайте два правила потока почты на основе информации в следующей таблице:

|Назначение  |Name |Примените это правило, если...             |Выполните следующие действия...                          |
|---------|-----|----------------------------------|---------------------------------------------|
|Правило для входящей эл. почты |Регистрировать сообщения электронной почты, присланные в эту организацию|*Отправитель* расположен *Вне организации*, и *получатель* расположен *Внутри организации*|Скрытая копия учетная запись электронной почты, указанная для общая папка *Очередь*|
|Правило для исходящей эл. почты | Регистрировать сообщения электронной почты, отправленные из этой организации |*Отправитель* расположен *Внутри организации*, и *получатель* расположен *Вне организации*|Скрытая копия учетная запись электронной почты, указанная для общая папка *Очередь*|

Дополнительные сведения см. в [Управлять правилами потока почты в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules?preserve-view=true) и [Действия правила потока почты в Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions?preserve-view=true).

> [!NOTE]
> Если вы вносите изменения в командной консоли Exchange, эти изменения становятся видимыми в центре администрирования Exchange через некоторое время. Также внесенные в Exchange изменения будут доступны в [!INCLUDE[prod_short](prod_short.md)] через некоторое время. Задержка может составить несколько часов.
