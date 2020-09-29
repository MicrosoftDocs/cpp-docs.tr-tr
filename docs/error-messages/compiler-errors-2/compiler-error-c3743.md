---
title: Derleyici hatası C3743
ms.date: 11/04/2016
f1_keywords:
- C3743
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
ms.openlocfilehash: b4bb198ae883e53e7947ce7f123bb0d3f092aaf3
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500398"
---
# <a name="compiler-error-c3743"></a>Derleyici hatası C3743

event_receiver ' layout_dependent ' parametresi true olduğunda, yalnızca bir arabirimin tamamını geri alabilir/kaldırır

[__Unhook](../../cpp/unhook.md) işlevi, `layout_dependent` [event_receiver](../../windows/attributes/event-receiver.md) sınıfındaki parametreye geçirilen değere göre gereken parametre sayısını gösterir.

Aşağıdaki örnek C3743 oluşturur:

```cpp
// C3743.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];
[object] __interface I { HRESULT f(); };

[event_receiver(com, layout_dependent=true), coclass]
struct R : I {
        HRESULT f() {
      return 0;
   }
        R() {
   }

   R(I* a) {
      __hook(I, a, &R::f);   // C3743
      // The following line resolves the error.
      // __hook(I, a);
   }
};
```
