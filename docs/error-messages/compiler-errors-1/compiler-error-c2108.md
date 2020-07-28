---
title: Derleyici hatası C2108
ms.date: 11/04/2016
f1_keywords:
- C2108
helpviewer_keywords:
- C2108
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
ms.openlocfilehash: cbbfa865682ac7423fccd9de4212d901f408810f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214782"
---
# <a name="compiler-error-c2108"></a>Derleyici hatası C2108

alt simge integral türünde değil

Dizi alt indisi tamsayı olmayan bir ifadedir.

## <a name="example"></a>Örnek

**`this`** Türün varsayılan dizin oluşturucusuna erişmek için bir değer türünün işaretçisini yanlış kullanırsanız C2108 oluşabilir. Daha fazla bilgi için [Bu Işaretçinin semantiğini](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)inceleyin.

Aşağıdaki örnek C2108 oluşturur.

```cpp
// C2108.cpp
// compile with: /clr
using namespace System;

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      Console::WriteLine("{0}", this[3.3]);   // C2108
      Console::WriteLine("{0}", this->default[3.3]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```
