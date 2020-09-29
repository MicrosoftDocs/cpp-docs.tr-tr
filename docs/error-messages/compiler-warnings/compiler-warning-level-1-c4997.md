---
title: Derleyici Uyarısı (düzey 1) C4997
ms.date: 11/04/2016
f1_keywords:
- C4997
helpviewer_keywords:
- C4997
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
ms.openlocfilehash: 15f96c6ab65eb5d9728e31e1cc9b31d0bc8aa9b2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499668"
---
# <a name="compiler-warning-level-1-c4997"></a>Derleyici Uyarısı (düzey 1) C4997

' class ': coclass bir COM arabirimi veya sahte arabirim uygulamıyor

[Coclass](../../windows/attributes/coclass.md) özniteliğiyle işaretlenmiş bir sınıf, bir arabirim gerçekleştirmedi.

Aşağıdaki örnek C4997 oluşturur:

```cpp
// C4997.cpp
// compile with: /WX
// to resolve this C4997, uncomment all code
#include <objbase.h>

[ object ]
__interface I {
   HRESULT func();
};

[ coclass ]
struct C /*: I*/ {
   /*
   HRESULT func() {
      return S_OK;
   }
   */
};   // C4997
```
