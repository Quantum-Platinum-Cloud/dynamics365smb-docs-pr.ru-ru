---
title: Настройка налогового учета в России
description: Российские улучшения включают налоговый учет.
author: DianaMalina
ms.topic: conceptual
ms.search.keywords: null
ms.date: 04/01/2021
ms.reviewer: edupont
ms.author: soalex
---

# <a name="set-up-tax-accounting" />Настройка налогового учета

Налоговый учет позволяет применять правила признания доходов и расходов в соответствии с местным законодательством. Вы можете активировать функции налогового учета в [!INCLUDE[prod_short](../../includes/prod_short.md)], настроив налоговые регистры.

## <a name="to-activate-tax-accounting" />Активация налогового учета

1. Выберите ![Лампочка, которая открывает функцию Что вы хотите сделать.](../../media/ui-search/search_small.png "Что вы хотите сделать") значок введите **Настройка налоговых регистров**, а затем выберите связанную ссылку.

2. На экспресс-вкладке **Общее** выберите коды для следующих измерений.

   | Поле                        | Описание                                                  |
   | :--------------------------- | :----------------------------------------------------------- |
   | **Условие - код измерения** | Выберите код измерения, описывающий условие налогового регистра. |
   | **Вид - код измерения**      | Выберите код измерения, описывающий тип налогового регистра. |

3. Выберите следующие поля, чтобы активировать операции в налоговом регистре.

   | Поле                             | Описание                                            |
   | :-------------------------------- | :----------------------------------------------------- |
   | **Создавать приобр. ОС в НУ**  | Выберите, чтобы создать операции приобретения ОС.      |
   | **Создавать рекласс. ОС в НУ** | Выберите, чтобы создать операции реклассификации ОС. |
   | **Создавать РБП по приобр. в НУ**  | Выберите, чтобы создать операции приобретения с учетом в будущих периодах.   |

4. Выберите соответствующие книги амортизации в полях **Книга амортизации для налогового учета** и **Расх. буд. пер. - книга аморт.**. Книги амортизации, которые вы выбрали, должны быть интегрированы с модулем финансов [!INCLUDE[prod_short](../../includes/prod_short.md)].

5. Установите флажок **Создать данные для печати форм**, чтобы разрешить печать подробных данных налогового регистра в отчетах и формах.

6. Нажмите кнопку **Закрыть**, чтобы закрыть окно и сохранить введенные данные.

Дополнительные сведения о том, как настроить налоговые регистры, см. в разделе [Создание налоговых регистров](How-to-Create-Tax-Registers.md).

## <a name="see-also" />См. также

[Налоговый учет](Tax-Accounting.md)  
[Налоговые регистры](Tax-Registers.md)  
[Расчет налоговых регистров](How-to-Create-Tax-Registers.md)  
[Налоговые разницы](Tax-Differences.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
