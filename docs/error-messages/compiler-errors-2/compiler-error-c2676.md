---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2676'
title: Derleyici hatası C2676
ms.date: 11/04/2016
f1_keywords:
- C2676
helpviewer_keywords:
- C2676
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
ms.openlocfilehash: ff620df72993d5c438e4f670dd63a2de56fea18e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281970"
---
# <a name="compiler-error-c2676"></a>Derleyici hatası C2676

ikili ' işleç ': ' Type ' Bu işleci veya önceden tanımlanmış işleç için kabul edilebilir bir türe dönüştürmeyi tanımlamıyor

İşlecini kullanmak için, belirtilen tür için onu tekrar yüklemelisiniz veya işlecin tanımlandığı bir türe dönüştürme tanımlamanız gerekir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2676 oluşturur.

```cpp
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

Ayrıca, **`this`** bir başvuru türünün İşaretçisinde işaretçi aritmetiği yapmayı denerseniz, C2676 de oluşabilir.

**`this`** İşaretçi, başvuru türünde tanıtıcı türünde. Daha fazla bilgi için [Bu Işaretçinin semantiğini](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)inceleyin.

Aşağıdaki örnek C2676 oluşturur.

```cpp
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
