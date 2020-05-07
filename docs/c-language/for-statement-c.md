---
title: for Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- for keyword [C]
ms.assetid: 560a8de4-19db-4868-9f18-dbe51b17900d
ms.openlocfilehash: df00bcab2f9f9e51a6f37e19670b6cd240fa5cc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233650"
---
# <a name="for-statement-c"></a>for Deyimi (C)

**For** deyimleri, bir ifadeyi veya bileşik ifadeyi belirtilen sayıda tekrarlamanızı sağlar. Bir **for** ifadesinin gövdesi, isteğe bağlı bir koşul false olana kadar sıfır veya daha fazla kez yürütülür. For **ifadesinin yürütmesi** sırasında değerleri başlatmak ve değiştirmek için **for** deyimi içinde isteğe bağlı ifadeleri kullanabilirsiniz.

## <a name="syntax"></a>Sözdizimi

*yineleme-ekstresi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**for** **(** *init-Expression*<sub>opt</sub> **;** *cond-expression*<sub>opt</sub> **;** *loop-expression*<sub>opt</sub> **)** *deyimi*

**For** ifadesinin yürütülmesi aşağıdaki gibi devam eder:

1. Varsa, *Init-ifadesi*değerlendirilir. Bu, döngü için başlatmayı belirtir. *İnit ifadesinin*türü üzerinde hiçbir kısıtlama yoktur.

1. Varsa, *cond-ifadesi*değerlendirilir. Bu ifade aritmetik veya işaretçi türünde olmalıdır. Her yinelemeden önce değerlendirilir. Üç sonuç mümkündür:

   - *Cond-expression* **true** ise (sıfır dışında), *deyim* yürütülür; ardından, varsa *döngü ifadesi*değerlendirilir. *Döngü ifadesi* Her yinelemeden sonra değerlendirilir. Türü üzerinde hiçbir kısıtlama yoktur. Yan etkiler sırayla yürütülür. Daha sonra işlem, *cond-expression*değerlendirmesiyle yeniden başlar.

   - *Cond-expression* atlanırsa, *cond ifadesi* true olarak kabul edilir ve yürütme, önceki paragrafta açıklandığı gibi tam olarak devam eder. *Cond-expression* bağımsız değişkeni olmayan bir **for** deyimi yalnızca deyim gövdesinin içindeki bir **Break** veya **Return** deyimi yürütüldüğünde veya bir **goto** ( **for** deyiminin ifadesi dışında bir etiketli ifadeye) yürütüldüğünde sona erer.

   - *Cond-expression* **false** (0) ise, **for** deyiminin yürütülmesi sonlanır ve denetim, programdaki sonraki deyime geçer.

**For** ifadesiyle bir **Break**, **goto**ya da **Return** deyimleri yürütüldüğünde de sonlanır. **For** döngüsünde **Continue** deyimi *döngü ifadesinin* değerlendirilmesine neden olur. **For** döngüsü içinde bir **Break** deyimi yürütüldüğünde, *Loop ifadesi* değerlendirilmez veya yürütülmez. Bu ifade

```C
for( ; ; )
```

yalnızca bir **Break**, **goto**veya **Return** ifadesiyle çıkılan sonsuz bir döngü oluşturmak için normal yoludur.

## <a name="example"></a>Örnek

Bu örnekte **for** ifadesinin gösterilmektedir:

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

## <a name="output"></a>Çıktı

```Output
Number of spaces: 4
Number of tabs: 2
```

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
