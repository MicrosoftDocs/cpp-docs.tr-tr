---
title: for Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- for keyword [C]
ms.assetid: 560a8de4-19db-4868-9f18-dbe51b17900d
ms.openlocfilehash: 91675fbe15ec6abf5aae4548990d9b4e0703e967
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229733"
---
# <a name="for-statement-c"></a>for Deyimi (C)

**`for`** İfade, bir ifadeyi veya bileşik ifadeyi belirtilen sayıda tekrarlamanızı sağlar. Bir deyimin gövdesi, **`for`** isteğe bağlı bir koşul false olana kadar sıfır veya daha fazla kez yürütülür. Deyimin **`for`** yürütülmesi sırasında değerleri başlatmak ve değiştirmek için deyimi içinde isteğe bağlı ifadeleri kullanabilirsiniz **`for`** .

## <a name="syntax"></a>Sözdizimi

*yineleme-ekstresi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`for`****(** *init-Expression*<sub>opt</sub> **;** *cond-expression*<sub>opt</sub> **;** *loop-expression*<sub>opt</sub> **)** *deyimi*

Bir deyimin yürütülmesi **`for`** Şu şekilde devam eder:

1. Varsa, *Init-ifadesi*değerlendirilir. Bu, döngü için başlatmayı belirtir. *İnit ifadesinin*türü üzerinde hiçbir kısıtlama yoktur.

1. Varsa, *cond-ifadesi*değerlendirilir. Bu ifade aritmetik veya işaretçi türünde olmalıdır. Her yinelemeden önce değerlendirilir. Üç sonuç mümkündür:

   - *Cond-expression* **`true`** (sıfır dışında) ise, *deyim* yürütülür; varsa, *döngü ifadesi*değerlendirilir. *Döngü ifadesi* Her yinelemeden sonra değerlendirilir. Türü üzerinde hiçbir kısıtlama yoktur. Yan etkiler sırayla yürütülür. Daha sonra işlem, *cond-expression*değerlendirmesiyle yeniden başlar.

   - *Cond-expression* atlanırsa, *cond ifadesi* true olarak kabul edilir ve yürütme, önceki paragrafta açıklandığı gibi tam olarak devam eder. **`for`** *Cond-expression* bağımsız değişkeni olmayan bir deyim yalnızca **`break`** deyim gövdesinde bir veya **`return`** deyimi yürütüldüğünde ya da **`goto`** (deyim gövdesi dışında bir etiketli ifadeye **`for`** ) yürütüldüğünde sonlanır.

   - *Cond-expression* **`false`** (0) ise, **`for`** deyiminin yürütülmesi sonlanır ve denetim, programdaki sonraki deyime geçer.

Deyimdeki **`for`** bir **`break`** , **`goto`** veya deyimleri yürütüldüğünde bir ifade da sonlanır **`return`** . **`continue`** Bir döngüsündeki deyim, **`for`** *döngü ifadesinin* değerlendirilmesine neden olur. Bir **`break`** deyim bir döngü içinde yürütüldüğünde **`for`** , *Loop ifadesi* değerlendirilmez veya yürütülmez. Bu ifade

```C
for( ; ; )
```

, yalnızca bir **`break`** , veya ifadesiyle çıkış olabilen sonsuz bir döngü oluşturmak için normal yoludur **`goto`** **`return`** .

## <a name="example"></a>Örnek

Bu örnek, **`for`** ifadesini göstermektedir:

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
