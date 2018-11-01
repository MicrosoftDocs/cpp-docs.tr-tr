---
title: Derleyici Hatası C3175
ms.date: 11/04/2016
f1_keywords:
- C3175
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
ms.openlocfilehash: 368e5a9cb9bea04a7889c25c86a7245049677112
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642708"
---
# <a name="compiler-error-c3175"></a>Derleyici Hatası C3175

'function1': 'function2' yönetilmeyen işlevinden bir yönetilen türün bir yöntemi çağrılamaz

Yönetilmeyen işlevleri yönetilen sınıflarının üye işlevleri çağrılamaz.

Aşağıdaki örnek, C3175 oluşturur:

```
// C3175_2.cpp
// compile with: /clr

ref struct A {
   static void func() {
   }
};

#pragma unmanaged   // remove this line to resolve

void func2() {
   A::func();   // C3175
}

#pragma managed

int main() {
   A ^a = gcnew A;
   func2();
}
```
