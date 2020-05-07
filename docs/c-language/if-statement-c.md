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
ms.openlocfilehash: b6df50d483a6e2958de3100a07c18b89b0c4f12f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233066"
---
# <a name="if-statement-c"></a>if Deyimi (C)

**IF** deyimleri koşullu dallanmayı denetler. İfadenin değeri sıfır değilse bir **IF** ifadesinin gövdesi yürütülür. **IF** ifadesinin sözdizimi iki form içerir.

## <a name="syntax"></a>Sözdizimi

*Selection-deyimi*: **if (**  *ifade*  **)**  *deyimi*

**IF (**  *Expression*  **)**  *deyimi*  **Else**  *deyimi*

Her iki **if** ifadesinin formlarında, bir yapı dışında herhangi bir değere sahip olabilen ifadeler, tüm yan etkiler dahil değerlendirilir.

Sözdiziminin ilk biçiminde, *ifade* true (sıfır dışında) ise *deyim* yürütülür. *İfade* yanlışsa, *deyim* yok sayılır. İkinci sözdizimi biçiminde, **başka**bir deyişle, *ifade* yanlışsa ikinci *deyim* yürütülür. Her iki form ile, deyimlerden biri bir **kesme**, **devam**veya ya `goto`da içermiyorsa, denetim daha sonra, **IF** deyiminden, programdaki bir sonraki ifadeye geçer.

**IF** ifadesinin örnekleri aşağıda verilmiştir:

```
if ( i > 0 )
    y = x / i;
else
{
    x = i;
    y = f( x );
}
```

Bu örnekte, ifadenin `y = x/i;` 0 ' dan büyük olması `i` durumunda yürütülür. `i` 0 ' dan küçük veya buna eşitse `i` , öğesine `x` atanır ve `f( x )` öğesine `y`atanır. **IF** yan tümcesini oluşturan deyimin noktalı virgülle bitdiğine unutmayın.

Deyimler ve **Else** yan **tümceleri iç içe aktardığınızda, deyimleri ve** yan tümceleri, amacınızı açıklığa kavuşturacak bileşik deyimlerde gruplamak için küme ayraçları kullanın. Hiçbir küme ayracı yoksa, derleyici, **başka**bir şey olmaması **durumunda** her **şeyi** En iyiyle ilişkilendirerek belirsizlikleri öğesini çözer.

```
if ( i > 0 )           /* Without braces */
    if ( j > i )
        x = j;
    else
        x = i;
```

**Else** yan tümcesi, bu örnekteki iç **if** ifadesiyle ilişkilendirilir. `i` 0 ' dan küçükse veya eşitse, hiçbir değer atanmaz `x`.

```
if ( i > 0 )
{                      /* With braces */
    if ( j > i )
        x = j;
}
else
    x = i;
```

Bu örnekteki iç **if** ifadesini çevreleyen küme ayraçları, dıştaki **if** ifadesinin **Else** yan tümcesini bir parçasını yapar. `i` 0 ' dan küçük veya buna eşitse, `i` öğesine `x`atanır.

## <a name="see-also"></a>Ayrıca bkz.

[if-else Deyimi (C++)](../cpp/if-else-statement-cpp.md)
