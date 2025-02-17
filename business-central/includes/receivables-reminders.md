---
author: edupont04
ms.topic: include
ms.date: 02/09/2022
ms.author: edupont
---
Можно использовать напоминания для напоминания клиентам о просроченных суммах. Также их можно использовать для вычисления финансовых расходов, таких как проценты или сборы, и их включения в напоминания.

Прежде чем создавать напоминания, необходимо настроить условия напоминания и назначить их клиентам. Дополнительные сведения см. в разделе [Настройка условий и уровней напоминаний](../finance-setup-reminders.md). [!INCLUDE [reminder-terms](reminder-terms.md)] Содержимое страницы **Процентные ставки** определяет, должен ли для напоминания вычисляться процент.  

Можно периодически выполнять пакетное задание **Создание напоминаний** для создания напоминаний для всех клиентов с просроченными задолженностями. Также можно вручную создать напоминание для определенного клиента, при этом автоматически вычислив и заполнив строки.  

После создания напоминаний их можно изменять. Текст, расположенный в начале и в конце напоминания, определяется уровнем напоминания, и его можно просмотреть в столбце **Описание**. Если вычисленная сумма была автоматически вставлена в начальный или заключительный текст, при удалении строк этот текст не будет корректироваться. В этом случае необходимо воспользоваться функцией **Обновить текст напоминания**.  

Для операции книги клиентов с заполненным полем **На удержании** создание напоминания не предлагается. Однако, если напоминание создается на основе другой операции, просроченная операция, помеченная как находящаяся на удержании, также будет включена в напоминание. Для строк, содержащих эти операции, процент не вычисляется.

После создания напоминаний и внесения всех необходимых изменений можно либо распечатать тестовые отчеты, либо сформировать напоминания, как правило по электронной почте.

### <a name="to-create-a-reminder-automatically" />Автоматическое создание напоминания

Напоминание подобно счету. При создании напоминания следует заполнить его заголовок и строки. Для автоматического создания напоминаний для всех клиентов можно использовать функцию.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать 0.](../media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Напоминания**, а затем выберите связанную ссылку.
2. На странице **Напоминание** выберите действие **Создать напоминания**.
3. На странице **Создание напоминаний** заполните все поля, чтобы определить, как и для кого создаются напоминания.
4. Нажмите кнопку **ОК**.

### <a name="to-create-a-reminder-manually" />Создание напоминания вручную

На странице **Напоминание** можно вручную заполнить экспресс-вкладку **Общее**, а затем автоматически заполнить строки.

1. Выберите ![Лампочка, которая снова открывает функцию Что вы хотите сделать 2.](../media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Напоминания**, а затем выберите связанную ссылку.
2. Выберите действие **Создать**.
3. На экспресс-вкладке **Общее** заполните необходимые поля.
4. Выберите действие **Предложить строки напоминания**.
5. В окне **Создание напоминаний** заполните все поля, чтобы определить, как и для кого создаются напоминания.
6. Установите флажок **Включить приостановленные записи**, чтобы напоминания содержали просроченные открытые приостановленные записи.
7. Установите флажок **Только операции с суммами просроченного платежа**, чтобы напоминания содержали только открытые записи с просрочкой. Будут отображаться только счета и платежи, поскольку только по этим операциям возможна просрочка платежей клиентов.

    > [!Important]
    > Приостановленные открытые записи будут вставляться независимо от состояния флажка **Только операции с суммами просроченного платежа**.

8. Нажмите кнопку **ОК**.

### <a name="to-replace-reminder-texts" />Замена текстов напоминаний

Существует несколько способов задания текста, появляющегося на распечатке напоминания. В некоторых случаях может потребоваться заменить начальный и конечный текст, заданный для текущего уровня, на текст, заданный для другого уровня.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать 3.](../media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Напоминания**, а затем выберите связанную ссылку.
2. Откройте соответствующее напоминание, а затем выберите действие **Обновить текст напоминания**.
3. На странице **Обновить текст напоминания** укажите требуемый уровень в поле **Уровень напоминания**.
4. Нажмите кнопку **ОК**, чтобы обновить начальный и конечный текст.

### <a name="to-issue-a-reminder" />Формирование напоминания

После создания напоминаний и внесения всех необходимых изменений можно либо распечатать тестовые отчеты, либо выдать напоминания.

При выдаче напоминания данные перемещаются на отдельную страницу для учтенных напоминаний. В то же время учитываются операции напоминаний. Если вычислен процент или дополнительный сбор, производится учет операций в книге клиентов и главной книге.

При выдаче напоминания записи учитываются в соответствии со спецификациями на странице **Условия напоминания**. Эта спецификация определяет, учитываются ли проценты и/или дополнительные сборы в счете клиента и главной книге. Параметры на странице **Учетные группы клиента** определяют счета, на которых учитываются операции.

По каждой учтенной клиентской операции в процент-ноте, создается операция на странице **Операции напоминания/процент-ноты**.

При наличии флажка в поле **Учет процентов** или в поле **Учет дополнительного сбора** страницы **Условия напоминания** также формируются следующие операции:

- одна операция на странице **Книга операций по клиентам**;
- одна операция "расчеты с клиентом" на соответствующем счете ГК;
- одна операция "процент" и/или "дополнительная плата" на соответствующем счете ГК.

Кроме того, учет процент-ноты может отразиться в операциях НДС.

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать 4 также здесь.](../media/ui-search/search_small.png "Что вы хотите сделать") значок, введите **Напоминания**, а затем выберите связанную ссылку.
2. Выберите соответствующее напоминание, в затем выберите действие **Выпустить**.
3. На странице **Выдача напоминаний** заполните требуемые поля.
4. Нажмите кнопку **ОК**

Напоминание печатается или отправляется по указанному адресу электронной почты как вложение PDF.

### <a name="to-cancel-an-issued-reminder" />Отмена выпущенного напоминания

Если напоминания были выпущены по ошибке, их можно отменить до того, как они будут разосланы. Отменять напоминания можно по одному или в пакетном режиме.

1. На странице **Отправленные напоминания** выберите одну или несколько строк выпущенных напоминаний, которые вы хотите отменить, а затем выберите действие **Отмена**.
2. На странице **Отменить отправленные напоминания** заполните поля требуемым образом, а затем выберите кнопку **ОК**.


