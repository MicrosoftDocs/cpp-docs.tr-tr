---
title: 'Çağırma Örneği: İşlev Prototipi ve Çağrı'
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: cbe9ee16db502c9e27dcbd74da4ef6a85f00960f
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857638"
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