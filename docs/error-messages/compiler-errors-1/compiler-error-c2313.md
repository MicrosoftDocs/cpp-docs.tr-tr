---
title: Derleyici hatası C2313
ms.date: 11/04/2016
f1_keywords:
- C2313
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
ms.openlocfilehash: 0eb085d9959359b31b022c2268f0ea8c7b811b20
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748131"
---
# <a name="compiler-error-c2313"></a>Derleyici hatası C2313

' type1 ': satır numarasında başvuruya (' type2 ') göre yakalandı

Özel durum türünün iki işleyicisi vardır. İkinci catch türü, ilk türünün bir başvurusudur.

Aşağıdaki örnek C2313 oluşturur:

```cpp
// C2313.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
    try {
        throw "ooops!";
    }
    catch( C& ) {}
    catch( C ) {}   // C2313
}
```
