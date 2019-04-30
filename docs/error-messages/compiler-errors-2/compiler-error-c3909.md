---
title: Derleyici Hatası C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: 95de97a27fc42e98247675b1b48325593ff3c21e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406528"
---
# <a name="compiler-error-c3909"></a>Derleyici Hatası C3909

aWinRT veya yönetilen bir olay bildirimi bir WinRT veya yönetilen türünde olmalıdır

Bir Windows çalışma zamanı olayı veya yönetilen bir olay, bir yerel türe bildirildi. Bu hatayı düzeltmek için Windows çalışma zamanı türleri ya da yönetilen türler olayları bildirin.

Daha fazla bilgi için [olay](../../extensions/event-cpp-component-extensions.md).

Aşağıdaki örnek, C3909 oluşturur ve bu sorunun nasıl gösterir:

```
// C3909.cpp
// compile with: /clr /c
delegate void H();
class X {
   event H^ E;   // C3909 - use ref class X instead
};

ref class Y {
   static event H^ E {
      void add(H^) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```