---
title: Derleyici Uyarısı (düzey 1) C4997
ms.date: 11/04/2016
f1_keywords:
- C4997
helpviewer_keywords:
- C4997
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
ms.openlocfilehash: ba5b2ec48c29b40ecb690cf9d222e518f91d219f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174407"
---
# <a name="compiler-warning-level-1-c4997"></a>Derleyici Uyarısı (düzey 1) C4997

' class ': coclass bir COM arabirimi veya sahte arabirim uygulamıyor

[Coclass](../../windows/coclass.md) özniteliğiyle işaretlenmiş bir sınıf, bir arabirim gerçekleştirmedi.

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
