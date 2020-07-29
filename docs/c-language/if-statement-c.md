---
title: if Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- else
- if
helpviewer_keywords:
- if keyword [C]
- else clauses
- else keyword [C]
- if keyword [C], if statement syntax
- nested statements
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
ms.openlocfilehash: 67cdae033c3c8669c8bc7ae1d2e3584ef68498f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227848"
---
# <a name="if-statement-c"></a>if Deyimi (C)

**`if`** İfade, koşullu dallanmayı denetler. **`if`** İfadenin değeri sıfır değilse deyimin gövdesi yürütülür. **`if`** Deyimin sözdiziminin iki formu vardır.

## <a name="syntax"></a>Sözdizimi

*Selection-deyimi*: **if (**  *ifade*  **)**  *deyimi*

**if (***ifade***)***deyim* **`else`** *deyimi*          

Her iki deyimin formlarında, **`if`** bir yapı dışında herhangi bir değere sahip olabilen ifadeler, tüm yan etkiler dahil değerlendirilir.

Sözdiziminin ilk biçiminde, *ifade* true (sıfır dışında) ise *deyim* yürütülür. *İfade* yanlışsa, *deyim* yok sayılır. Öğesinin kullanıldığı ikinci sözdizimi biçiminde **`else`** , *ifade* false ise ikinci *deyim* yürütülür. Her iki form ile, **`if`** deyimlerden biri, veya içermiyorsa, denetim daha sonra deyimden programdaki sonraki deyime geçer **`break`** **`continue`** **`goto`** .

Aşağıda deyimin örnekleri verilmiştir **`if`** :

```
if ( i > 0 )
    y = x / i;
else
{
    x = i;
    y = f( x );
}
```

Bu örnekte, ifadenin 0 ' `y = x/i;` `i` dan büyük olması durumunda yürütülür. `i`0 ' dan küçük veya buna eşitse, `i` öğesine atanır `x` ve `f( x )` öğesine atanır `y` . **`if`** Yan tümcesini oluşturan deyimin noktalı virgülle bitdiğine unutmayın.

**`if`** Deyimleri ve yan tümceleri iç içe geçirerek **`else`** , deyimleri ve yan tümceleri, amacınızı açıklığa kavuşturacak bileşik deyimlerde gruplamak için ayraçları kullanın. Hiçbir küme ayracı yoksa, derleyici, her biri olmayan en yakın ile ilişkilendirerek belirsizlikleri öğesini çözer **`else`** **`if`** **`else`** .

```
if ( i > 0 )           /* Without braces */
    if ( j > i )
        x = j;
    else
        x = i;
```

**`else`** Yan tümcesi, **`if`** Bu örnekteki Inner ifadesiyle ilişkilendirilir. `i`0 ' dan küçükse veya eşitse, hiçbir değer atanmaz `x` .

```
if ( i > 0 )
{                      /* With braces */
    if ( j > i )
        x = j;
}
else
    x = i;
```

Bu örnekteki iç deyimi çevreleyen parantezler, **`if`** **`else`** dış deyimin yan tümcesini yapar **`if`** . `i`0 ' dan küçük veya buna eşitse, `i` öğesine atanır `x` .

## <a name="see-also"></a>Ayrıca bkz.

[if-else Deyimi (C++)](../cpp/if-else-statement-cpp.md)
