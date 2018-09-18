---
title: varsa Statement (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- else
- if
dev_langs:
- C++
helpviewer_keywords:
- if keyword [C]
- else clauses
- else keyword [C]
- if keyword [C], if statement syntax
- nested statements
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b01db4d842775dcb239aef9d40c661328d1544
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107885"
---
# <a name="if-statement-c"></a>if Deyimi (C)

**Varsa** deyimi, koşullu dallanmayı denetler. Gövdesi bir **varsa** deyimi ifade değeri sıfır ise yürütülür. Sözdizimi **varsa** deyiminin iki biçimini şunlardır.

## <a name="syntax"></a>Sözdizimi

*Seçimi deyimi*: **varsa (***ifade***)***deyimi* 

**varsa (***ifade***)***deyimi***başka***deyimi* 

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

## <a name="see-also"></a>Ayrıca Bkz.

[if-else Deyimi (C++)](../cpp/if-else-statement-cpp.md)