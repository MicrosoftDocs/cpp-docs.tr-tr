---
title: İfade Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
ms.openlocfilehash: 736ed4fbbd9f87c675c0bb9566c6c31287e77917
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148796"
---
# <a name="expression-statement-c"></a>İfade Deyimi (C)

Bir ifade deyimi yürütüldüğünde, ifade içinde açıklanan kurallara göre değerlendirilir [ifadeler ve atamalar](../c-language/expressions-and-assignments.md).

## <a name="syntax"></a>Sözdizimi

*ifade deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade*<sub>iyileştirilmiş</sub> **;**

İfade değerlendirmesinden gelen tüm yan etkiler, sonraki deyim yürütülmeden önce tamamlanır. Boş ifade deyimine null deyim denir. Bkz: [Null deyim](../c-language/null-statement-c.md) daha fazla bilgi için.

Bu örnekler, ifade deyimlerini gösterir.

```C
x = ( y + 3 );            /* x is assigned the value of y + 3  */
x++;                      /* x is incremented                  */
x = y = 0;                /* Both x and y are initialized to 0 */
proc( arg1, arg2 );       /* Function call returning void      */
y = z = ( f( x ) + 3 );   /* A function-call expression        */
```

Son deyim olan işlev çağrısı ifadesinde, işlev tarafından döndürülen tüm değerleri içeren ifade değeri 3 artırılır ve ardından hem `y` hem de `z` değişkenine atanır.

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../c-language/statements-c.md)
