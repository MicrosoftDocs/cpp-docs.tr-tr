---
title: Derleyici Hatası C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 8174faed09bdffbdc6974390cceb7c17661eab4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388780"
---
# <a name="compiler-error-c2885"></a>Derleyici Hatası C2885

'class::identifier': değil bir geçerli using bildirimi sınıf olmayan kapsamda

Kullanılan bir [kullanarak](../../cpp/using-declaration.md) bildirimi yanlış.

## <a name="example"></a>Örnek

Bu hata için Visual C++ 2005 yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulan: artık sahip için geçerli olan bir `using` ; iç içe geçmiş bir tür bildirimine türü bir ad put iç içe türü, yaptığınız her başvurunun açıkça nitelemeniz gerekir boşluk veya bir tür tanımı oluşturun.

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