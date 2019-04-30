---
title: 'Çağırma örneği: İşlev prototipi ve çağrı'
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: f89f4f1917810baa585dd1661428e0809b93cca0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345105"
---
# <a name="calling-example-function-prototype-and-call"></a>Çağırma örneği: İşlev prototipi ve çağrı

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