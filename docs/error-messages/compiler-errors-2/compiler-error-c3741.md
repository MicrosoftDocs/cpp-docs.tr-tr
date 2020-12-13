---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3741'
title: Derleyici hatası C3741
ms.date: 11/04/2016
f1_keywords:
- C3741
helpviewer_keywords:
- C3741
ms.assetid: ed311315-cc32-49c9-97fa-01b293d81526
ms.openlocfilehash: 158555995449416da23120cafe16262cbb1a6208
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340261"
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
