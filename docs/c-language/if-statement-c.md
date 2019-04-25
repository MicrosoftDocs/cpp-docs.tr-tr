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

**Varsa** deyimi, koşullu dallanmayı denetler. Gövdesi bir **varsa** deyimi ifade değeri sıfır ise yürütülür. Sözdizimi **varsa** deyiminin iki biçimini şunlardır.

## <a name="syntax"></a>Sözdizimi

*Seçimi deyimi*: **varsa (** *ifade* **)** *deyimi*

**varsa (** *ifade* **)** *deyimi* **başka** *deyimi*

Her iki formu içinde **varsa** deyimi, bir yapı dışında herhangi bir değere sahip olabilir, ifadeler değerlendirilir, tüm yan etkileri de dahil olmak üzere.

Söz dizimi ilk biçiminde değilse *ifade* true (sıfırdan farklı), *deyimi* yürütülür. Varsa *ifade* false ise *deyimi* göz ardı edilir. İkinci sözdizimi formunda, kullanan **başka**, ikinci *deyimi* yürütülür *ifade* false'tur. Her iki biçimi sonra geçişlerinin denetim **varsa** deyimi programdaki sonraki deyime deyimlerden biri içermiyorsa bir **kesme**, **devam**, veya `goto`.

Aşağıdaki örnekler **varsa** deyimi:

```
if ( i > 0 )
    y = x / i;
else
{
    x = i;
    y = f( x );
}
```

Bu örnekte, deyim `y = x/i;` yürütülür `i` 0'dan büyük. Varsa `i` 0, küçük veya ona eşit `i` atandığı `x` ve `f( x )` atandığı `y`. Oluşturan deyim unutmayın **varsa** yan tümcesi, noktalı virgül ile sona erer.

İç içe olduğunda **varsa** deyimleri ve **başka** yan tümcesi, amacı açıklamak bileşik açıklamaalarını deyimleri ve yan tümcelerini gruplandırmak için ayraç kullanın. Hiç küme ayraçları mevcut olması durumunda, derleyici belirsizlikleri her ilişkilendirerek çözümler **başka** en yakın olan **varsa** , eksik bir **başka**.

```
if ( i > 0 )           /* Without braces */
    if ( j > i )
        x = j;
    else
        x = i;
```

**Başka** yan tümcesi iç ile ilişkili **varsa** Bu örnekte bildirimi. Varsa `i` küçük veya buna eşit olduğu için hiçbir değer 0'a atanır `x`.

```
if ( i > 0 )
{                      /* With braces */
    if ( j > i )
        x = j;
}
else
    x = i;
```

İç çevreleyen parantezler **varsa** Bu örnekte deyimi yap **başka** dış yan tümcesi parçası **varsa** deyimi. Varsa `i` 0, küçük veya ona eşit `i` atandığı `x`.

## <a name="see-also"></a>Ayrıca bkz.

[if-else Deyimi (C++)](../cpp/if-else-statement-cpp.md)
