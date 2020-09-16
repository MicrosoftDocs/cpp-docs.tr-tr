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
ms.openlocfilehash: 6fe92d3f2927cd6c5b3df16850e2925fc42055d0
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684150"
---
# <a name="if-statement-c"></a>if Deyimi (C)

**`if`** İfade, koşullu dallanmayı denetler. **`if`** İfadenin değeri sıfır değilse deyimin gövdesi yürütülür. **`if`** Deyimin sözdiziminin iki formu vardır.

## <a name="syntax"></a>Syntax

*Selection-deyimi*: **if (**  *ifade*  **)**  *deyimi*

**if (***ifade***)***deyim* **`else`** *deyimi*          

Her iki deyimin formlarında, **`if`** bir yapı dışında herhangi bir değere sahip olabilen ifadeler, tüm yan etkiler dahil değerlendirilir.

Sözdiziminin ilk biçiminde, *ifade* true (sıfır dışında) ise *deyim* yürütülür. *İfade* yanlışsa, *deyim* yok sayılır. Öğesinin kullanıldığı ikinci sözdizimi biçiminde **`else`** , *ifade* false ise ikinci *deyim* yürütülür. Her iki form ile, **`if`** deyimlerden biri, veya içermiyorsa, denetim daha sonra deyimden programdaki sonraki deyime geçer **`break`** **`continue`** **`goto`** .

Aşağıda deyimin örnekleri verilmiştir **`if`** :

```C
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

```C
if ( i > 0 )           /* Without braces */
    if ( j > i )
        x = j;
    else
        x = i;
```

**`else`** Yan tümcesi, **`if`** Bu örnekteki Inner ifadesiyle ilişkilendirilir. `i`0 ' dan küçükse veya eşitse, hiçbir değer atanmaz `x` .

```C
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
