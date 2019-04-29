---
title: Derleyici Hatası C2108
ms.date: 11/04/2016
f1_keywords:
- C2108
helpviewer_keywords:
- C2108
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
ms.openlocfilehash: 3979fce67f1ecb7f78bd02d4f1c4d2cca287ceca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364564"
---
# <a name="compiler-error-c2108"></a>Derleyici Hatası C2108

İNDİS tam sayı türünde değil.

Dizi alt simge işlemesinin ifadesidir.

## <a name="example"></a>Örnek

Yanlış kullanırsanız C2108 oluşabilir `this` türün varsayılan dizin oluşturucu erişmek için bir değer türünün işaretçisi. Daha fazla bilgi için [semantiği Bu işaretçi](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).

Aşağıdaki örnek, C2108 oluşturur.

```
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