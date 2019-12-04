---
title: Derleyici hatası C3741
ms.date: 11/04/2016
f1_keywords:
- C3741
helpviewer_keywords:
- C3741
ms.assetid: ed311315-cc32-49c9-97fa-01b293d81526
ms.openlocfilehash: 2be5c0a4f85448f41f865bdde79d56998fbcf16a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752606"
---
# <a name="compiler-error-c3741"></a>Derleyici hatası C3741

' class ': event_receiver = true olan ' layout_dependent ' parametresi olduğunda bir coclass olmalıdır

Bir [event_receiver](../../windows/event-receiver.md) sınıfı için `layout_dependent=true`, sınıfın [coclass](../../windows/coclass.md) özniteliği de olmalıdır.

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
