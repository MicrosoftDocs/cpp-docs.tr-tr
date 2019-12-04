---
title: Derleyici hatası C3708
ms.date: 11/04/2016
f1_keywords:
- C3708
helpviewer_keywords:
- C3708
ms.assetid: 45e71564-9c7f-437f-98d8-a735ce162ed0
ms.openlocfilehash: b5a2688cf138733a7a2891238953bc9fd894e483
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757975"
---
# <a name="compiler-error-c3708"></a>Derleyici hatası C3708

' interface ': ' anahtar sözcük ' yanlış kullanımı; uyumlu bir olay kaynağının üyesi olmalıdır

Bir arabirimi olay olarak bildirmek için, olay bildiriminin bir olay kaynağında olması gerekir.

Aşağıdaki örnek C3708 oluşturur:

```cpp
// C3708.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="MyLibrary")];

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I {
   HRESULT func();
};

[ object, uuid("00000000-0000-0000-0000-000000000002") ]
__interface II {
   HRESULT func();
};

__event __interface I;   // C3708

// put the event in an event source
[ coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000003") ]
struct E : II {
   __event __interface II;
};
```
