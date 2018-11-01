---
title: 'Çağırma Örneği: İşlev Prototipi ve Çağrı'
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: f89f4f1917810baa585dd1661428e0809b93cca0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508192"
---
# <a name="calling-example-function-prototype-and-call"></a>Çağırma Örneği: İşlev Prototipi ve Çağrı

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Aşağıdaki örnek, çeşitli çağırma kurallarını kullanarak bir işlevi çağırmak sonuçlarını gösterir.

Bu örnek, aşağıdaki işlev çatıyı üzerinde temel alır. Değiştirin `calltype` uygun çağırma kuralı.

```
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

Daha fazla bilgi için [çağırma örneği sonuçları](../cpp/results-of-calling-example.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)