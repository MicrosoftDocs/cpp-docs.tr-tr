---
title: İfade Statement (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73071e5cc3eef20895e4eff3bade8e37066dfd71
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765963"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Deyimler](../c-language/statements-c.md)