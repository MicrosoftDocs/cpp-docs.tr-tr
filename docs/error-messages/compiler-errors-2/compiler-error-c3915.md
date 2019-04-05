---
title: Derleyici Hatası C3915
ms.date: 11/04/2016
f1_keywords:
- C3915
helpviewer_keywords:
- C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
ms.openlocfilehash: 85654e266c3157ab145e7ac7aab454a0d4f6c102
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776460"
---
# <a name="compiler-error-c3915"></a>Derleyici Hatası C3915

'type' hiçbir varsayılan dizini oluşturulan özelliğe (sınıf dizini oluşturucu) vardır.

Bir tür bir varsayılan, dizinlenmiş özellik yok.

Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3915 oluşturur.

```
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

C3915 de burada bu tanımlandı ile aynı derlenecek bir varsayılan dizin oluşturucusunu kullanma çalışırsanız da gerçekleşebilir <xref:System.Reflection.DefaultMemberAttribute>.

Aşağıdaki örnek, C3915 oluşturur.

```
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