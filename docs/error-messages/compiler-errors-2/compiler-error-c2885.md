---
title: Derleyici Hatası C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: ff5e770052301e95f694d3712f95b82732c2faba
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447691"
---
# <a name="compiler-error-c2885"></a>Derleyici Hatası C2885

'class::identifier': değil bir geçerli using bildirimi sınıf olmayan kapsamda

Kullanılan bir [kullanarak](../../cpp/using-declaration.md) bildirimi yanlış.

## <a name="example"></a>Örnek

Bu hata için Visual Studio 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: artık sahip için geçerli olan bir `using` ; iç içe geçmiş bir tür bildirimine türü bir n put iç içe türü, yaptığınız her başvurunun açıkça nitelemeniz gerekir amespace, veya bir tür tanımı oluşturun.

Aşağıdaki örnek, C2885 oluşturur.

```
// C2885.cpp
namespace MyNamespace {
   class X1 {};
}

struct MyStruct {
   struct X1 {
      int i;
   };
};

int main () {
   using MyStruct::X1;   // C2885

   // OK
   using MyNamespace::X1;
   X1 myX1;

   MyStruct::X1 X12;

   typedef MyStruct::X1 abc;
   abc X13;
   X13.i = 9;
}
```

## <a name="example"></a>Örnek

Kullanırsanız `using` anahtar sözcüğü bir sınıf üyesinin, C++ ile başka bir sınıf (türetilmiş bir sınıf) içinde bu üye tanımlamanızı gerektirir.

Aşağıdaki örnek, C2885 oluşturur.

```
// C2885_b.cpp
// compile with: /c
class A {
public:
   int i;
};

void z() {
   using A::i;   // C2885 not in a class
}

class B : public A {
public:
   using A::i;
};
```