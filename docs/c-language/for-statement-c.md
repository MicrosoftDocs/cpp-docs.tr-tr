---
title: Statement (C) için | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C]
ms.assetid: 560a8de4-19db-4868-9f18-dbe51b17900d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6ad4b23e6caef15b5dabaaa3102d72e3ff84fbc
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860595"
---
# <a name="for-statement-c"></a>for Deyimi (C)

**İçin** deyimi bir deyim yineleyin veya bileşik deyim, belirtilen sayıda olanak sağlar. Gövdesi bir **için** deyimi, isteğe bağlı bir koşul false olana kadar sıfır veya daha fazla kez yürütülür. İsteğe bağlı ifade içinde kullanabilirsiniz **için** başlatıp sırasında değerlerini değiştirmek için deyimi **için** deyimin yürütme.

## <a name="syntax"></a>Sözdizimi

*Yineleme deyiminin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**için** **(** *init-expression*<sub>iyileştirilmiş</sub> **;** *; cond-expression*<sub>iyileştirilmiş</sub> **;** *döngü ifadesi*<sub>iyileştirilmiş</sub> **)** *deyimi*

Yürütülmesini bir **için** deyimi aşağıdaki gibi ilerler:

1. *İnit-expression*, varsa, değerlendirilir. Bu döngü için başlatma belirtir. Tür bir kısıtlama yoktur *init-expression*.

1. *; Cond-expression*, varsa, değerlendirilir. Bu ifade aritmetik veya işaretçi türünde olmalıdır. Her yinelemeden önce değerlendirilir. Üç sonuçları desteklenir:

   - Varsa *; cond-expression* olduğu **true** (sıfırdan farklı) *deyimi* yürütülür; ardından *döngü ifadesi*, varsa, değerlendirme. *Döngü ifadesi* her yinelemeden sonra değerlendirilir. Türü konusunda bir kısıtlama yoktur. Yan etkileri sırayla yürütülür. İşlem daha sonra yeniden değerlendirmesi ile başlar *; cond-expression*.

   - Varsa *; cond-expression* atlanırsa, *; cond-expression* true ve yürütme devam eder, tam olarak önceki paragrafta açıklandığı gibi değerlendirilir. A **için** deyimi olmadan bir *; cond-expression* bağımsız değişkeni yalnızca sonlandıran bir **sonu** veya **dönüş** deyimi deyimi içinde gövdesi yürütülür veya ne zaman bir **goto** (dışında etiketli deyime **için** deyim gövdesi) yürütülür.

   - Varsa *; cond-expression* olduğu **false** (0) yürütülmesini **için** deyimi sonlanır ve denetim geçer programdaki sonraki deyime.

A **için** deyimi de sonlandırılır bir **sonu**, **goto**, veya **dönüş** deyimi deyim gövdesi içinde yürütülür. A **devam** deyiminde bir **için** döngüye neden *döngü ifadesi* değerlendirilecek. Olduğunda bir **kesme** içinde deyimi yürütüldüğünde bir **için** döngü *döngü ifadesi* değerlendirilen yürütülen ya da. Bu bildirimi

```C
for( ; ; )
```

yalnızca ile çıkılması, sonsuz bir döngü oluşturmak için her zamanki yolu bir **sonu**, **goto**, veya **dönüş** deyimi.

## <a name="example"></a>Örnek

Bu örnekte **için** deyimi:

```C
// c_for.c
int main()
{
   char* line = "H e  \tl\tlo World\0";
   int space = 0;
   int tab = 0;
   int i;
   int max = strlen(line);
   for (i = 0; i < max; i++ )
   {
      if ( line[i] == ' ' )
      {
          space++;
      }
      if ( line[i] == '\t' )
      {
          tab++;
      }
   }

   printf("Number of spaces: %i\n", space);
   printf("Number of tabs: %i\n", tab);
   return 0;
}
```

## <a name="output"></a>Çıkış

```Output
Number of spaces: 4
Number of tabs: 2
```

## <a name="see-also"></a>Ayrıca Bkz.

[Deyimler](../c-language/statements-c.md)
