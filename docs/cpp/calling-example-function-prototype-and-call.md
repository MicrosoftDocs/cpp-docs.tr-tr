---
description: 'Daha fazla bilgi edinin: çağırma örneği: Işlev prototipi ve çağrı'
title: 'Çağırma Örneği: İşlev Prototipi ve Çağrı'
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: d7d8b68abc030e12d10fc5daa8b56f793d3ea14a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335594"
---
# <a name="calling-example-function-prototype-and-call"></a>Çağırma Örneği: İşlev Prototipi ve Çağrı

**Microsoft'a Özgü**

Aşağıdaki örnek, çeşitli çağırma kurallarını kullanarak işlev çağrısı yapma sonuçlarını gösterir.

Bu örnek, aşağıdaki işlev iskelet ' i temel alır. `calltype`Uygun çağırma kuralıyla değiştirin.

```cpp
void    calltype MyFunc( char c, short s, int i, double f );
.
.
.
void    MyFunc( char c, short s, int i, double f )
    {
    .
    .
    .
    }
.
.
.
MyFunc ('x', 12, 8192, 2.7183);
```

Daha fazla bilgi için bkz. [çağırma sonuçları](../cpp/results-of-calling-example.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma kuralları](../cpp/calling-conventions.md)
