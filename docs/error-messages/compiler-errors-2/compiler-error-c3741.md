---
title: Derleyici hatası C3741
ms.date: 11/04/2016
f1_keywords:
- C3741
helpviewer_keywords:
- C3741
ms.assetid: ed311315-cc32-49c9-97fa-01b293d81526
ms.openlocfilehash: e551fa3dbf67d2158081bea9d19051d4703d9c43
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501312"
---
# <a name="compiler-error-c3741"></a>Derleyici hatası C3741

' class ': event_receiver = true olan ' layout_dependent ' parametresi olduğunda bir coclass olmalıdır

`layout_dependent=true` [Event_receiver](../../windows/attributes/event-receiver.md) sınıfı için, sınıfın [coclass](../../windows/attributes/coclass.md) özniteliği de olmalıdır.

Aşağıdaki örnek C3741 oluşturur

```cpp
// C3741.cpp
// compile with: /c
// C3741 expected
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface I{ HRESULT f(); };

// Delete the following line to resolve.
[ event_receiver(com, layout_dependent=true)]

// class or struct must be declared with coclass
// Uncomment the following line to resolve.
// [ event_receiver(com, layout_dependent=true), coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct R : I {
   HRESULT f(){ return 0; }
   R(){}
   R(I* a){ __hook(I, a); }
};
```
