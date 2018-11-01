---
title: Derleyici Hatası C3745
ms.date: 11/04/2016
f1_keywords:
- C3745
helpviewer_keywords:
- C3745
ms.assetid: 1e64aec5-7e53-47e5-bc7d-3905230cfc66
ms.openlocfilehash: da80a10cbf7246ad0aeaecffe20992d2050abb3c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637872"
---
# <a name="compiler-error-c3745"></a>Derleyici Hatası C3745

'function': yalnızca bir olay 'Raise' yapılabilir

Yalnızca ile tanımlanan bir işlev [__event](../../cpp/event.md) anahtar sözcüğü geçilebilir [__raise](../../cpp/raise.md) anahtar sözcüğü.

Aşağıdaki örnek, C3745 oluşturur:

```
// C3745.cpp
struct E {
   __event void func();
   void func(int) {
   }

   void func2() {
   }

   void bar() {
      __raise func();
      __raise func(1);   // C3745
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func();
   __raise e.func(1);   // C3745
   __raise e.func2();   // C3745
}
```