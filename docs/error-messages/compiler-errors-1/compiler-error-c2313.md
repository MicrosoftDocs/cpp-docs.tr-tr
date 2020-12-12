---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2313'
title: Derleyici hatası C2313
ms.date: 11/04/2016
f1_keywords:
- C2313
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
ms.openlocfilehash: 455bc3a833f576c051ff1531d921f8504789810e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282165"
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
