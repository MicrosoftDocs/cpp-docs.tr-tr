---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2387'
title: Derleyici hatası C2387
ms.date: 11/04/2016
f1_keywords:
- C2387
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
ms.openlocfilehash: 70c876c999ec7d40b93ac94ffe111d105981ceeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124013"
---
# <a name="compiler-error-c2387"></a>Derleyici hatası C2387

' Type ': belirsiz taban sınıf

İşlev birden fazla temel sınıfta olduğundan, derleyici bir işlev çağrısını kesin olarak çözümleyemedi.

Bu hatayı çözmek için, devralmadan temel sınıflardan birini kaldırın ya da işlev çağrısını açıkça niteleyin.

Aşağıdaki örnek C2387 oluşturur:

```cpp
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
