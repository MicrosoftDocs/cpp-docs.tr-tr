---
title: Derleyici Hatası C2313
ms.date: 11/04/2016
f1_keywords:
- C2313
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
ms.openlocfilehash: 276dea87770035967a08ca5ac3e95316832ffc1b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641083"
---
# <a name="compiler-error-c2313"></a>Derleyici Hatası C2313

'type1': satır numarasında başvuru ('type2') tarafından yakalandı

Özel durum türü, iki işleyicileri vardır. İkinci yakalama ilk türü bir başvuru türüdür.

Aşağıdaki örnek, C2313 oluşturur:

```
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