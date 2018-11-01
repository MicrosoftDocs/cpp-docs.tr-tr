---
title: Derleyici Hatası C2387
ms.date: 11/04/2016
f1_keywords:
- C2387
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
ms.openlocfilehash: df9e92bfa333be88e860bbdecd5acaa64ec80440
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629313"
---
# <a name="compiler-error-c2387"></a>Derleyici Hatası C2387

'type': belirsiz taban sınıfı

Birden fazla temel sınıfta işlevi var olduğundan derleyici bir işlev çağrısı belirsiz çözümlenemedi.

Bu hatayı gidermek için temel sınıflarının biri öğesinden devralmayı kaldırın veya açıkça işlev çağrısı niteleyin.

Aşağıdaki örnek, C2387 oluşturur:

```
// C2387.cpp
namespace N1 {
   struct B {
      virtual void f() {
      }
   };
}

namespace N2 {
   struct B {
      virtual void f() {
      }
   };
}

struct D : N1::B, N2::B {
   virtual void f() {
      B::f();   // C2387
      // try the following line instead
      // N1::B::f();
   }
};

int main() {
   D aD;
   aD.f();
}
```