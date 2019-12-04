---
title: Derleyici hatası C3915
ms.date: 11/04/2016
f1_keywords:
- C3915
helpviewer_keywords:
- C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
ms.openlocfilehash: 26fdcd3b7989d9030249133e6dc1d277aa1a9f44
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756285"
---
# <a name="compiler-error-c3915"></a>Derleyici hatası C3915

' Type ' için Default dizinli özelliği yok (sınıf Dizin Oluşturucu)

Bir türün varsayılan, dizinli bir özelliği yok.

Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3915 oluşturur.

```cpp
// C3915.cpp
// compile with: /clr
ref class X {
public:
// uncomment property to resolve this C3915
//   property int default[]
//   {
//      int get(int i)
//      {
//         return 863;
//      }
//   }
};

int main() {
   X^ x = new X;
   System::Console::WriteLine(x[1]);   // C3915
}
```

## <a name="example"></a>Örnek

C3915, aynı compiland içinde <xref:System.Reflection.DefaultMemberAttribute>ile tanımlandığı yerde varsayılan bir dizin oluşturucuyu kullanmaya çalışırsanız da oluşabilir.

Aşağıdaki örnek C3915 oluşturur.

```cpp
// C3915_b.cpp
// compile with: /clr
using namespace System;

[Reflection::DefaultMember("XXX")]
ref struct A {
   property Double XXX[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

ref struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

int main() {
   A ^ mya = gcnew A();
   Console::WriteLine("{0}", mya[3]);   // C3915

   B ^ myb = gcnew B();
   Console::WriteLine("{0}", myb[3]);   // OK
}
```
