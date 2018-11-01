---
title: Derleyici Hatası C2676
ms.date: 11/04/2016
f1_keywords:
- C2676
helpviewer_keywords:
- C2676
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
ms.openlocfilehash: 1a3eab8d1df7534f2bfbed42db5c1a660942eacc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608084"
---
# <a name="compiler-error-c2676"></a>Derleyici Hatası C2676

İkili 'operator': 'type' bu işleci veya tanımlamıyor kabul edilebilir bir türe dönüştürme için önceden tanımlanmış işleç

İşlecini kullanmak için belirtilen tür için aşırı veya tanımlar işlecin tanımlandığı bir türe dönüştürmeyi gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2676 oluşturur.

```
// C2676.cpp
// C2676 expected
struct C {
   C();
} c;

struct D {
   D();
   D operator >>( C& ){return * new D;}
   D operator <<( C& ){return * new D;}
} d;

struct E {
   // operator int();
};

int main() {
   d >> c;
   d << c;
   E e1, e2;
   e1 == e2;   // uncomment operator int in class E, then
               // it is OK even though neither E::operator==(E) nor
               // operator==(E, E) defined. Uses the conversion to int
               // and then the builtin-operator==(int, int)
}
```

## <a name="example"></a>Örnek

C2676 üzerinde işaretçi aritmetik yapmayı denerseniz de oluşabilir `this` başvuru türü işaretçi.

`this` Başvuru türündeki tür tanıtıcının işaretçisidir. Daha fazla bilgi için [semantiği Bu işaretçi](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).

Aşağıdaki örnek, C2676 oluşturur.

```
// C2676_a.cpp
// compile with: /clr
using namespace System;

ref struct A {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }

   A() {
      Console::WriteLine("{0}", this + 3.3);   // C2676
      Console::WriteLine("{0}", this[3.3]);   // OK
   }
};

int main() {
   A ^ mya = gcnew A();
}
```