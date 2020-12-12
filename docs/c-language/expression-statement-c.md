---
description: 'Daha fazla bilgi edinin: Ifade deyimi (C)'
title: İfade Deyimi (C)
ms.date: 11/04/2016
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
ms.openlocfilehash: b7bd4b0bac73277cedfd1e651ba731715a083b72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196444"
---
# <a name="expression-statement-c"></a>İfade Deyimi (C)

Bir ifade deyimi yürütüldüğünde, ifade [ifadelerde ve atamalarda](../c-language/expressions-and-assignments.md)özetlenen kurallara göre değerlendirilir.

## <a name="syntax"></a>Syntax

*ifade ifadesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ifade*<sub>katılımı</sub> **;**

İfade değerlendirmesinden gelen tüm yan etkiler, sonraki deyim yürütülmeden önce tamamlanır. Boş ifade deyimine null deyim denir. Daha fazla bilgi için bkz. [null bildirisi](../c-language/null-statement-c.md) .

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
