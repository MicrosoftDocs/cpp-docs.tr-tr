---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3743'
title: Derleyici hatası C3743
ms.date: 11/04/2016
f1_keywords:
- C3743
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
ms.openlocfilehash: 1afad204f25220df53d58313a5742424e3491710
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340248"
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
