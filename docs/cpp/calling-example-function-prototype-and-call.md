---
title: 'Çağırma Örneği: İşlev Prototipi ve Çağrı'
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: c41d7679be8b7faa3c8df1368d14815a1b840284
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190176"
---
# <a name="calling-example-function-prototype-and-call"></a>Çağırma Örneği: İşlev Prototipi ve Çağrı

**Microsoft 'a özgü**

Aşağıdaki örnek, çeşitli çağırma kurallarını kullanarak işlev çağrısı yapma sonuçlarını gösterir.

Bu örnek, aşağıdaki işlev iskelet ' i temel alır. `calltype` uygun çağırma kuralıyla değiştirin.

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

[Çağırma Kuralları](../cpp/calling-conventions.md)
