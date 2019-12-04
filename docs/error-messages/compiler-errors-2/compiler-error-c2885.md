---
title: Derleyici hatası C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: e60f3fff2ef61f4d6374072c05a2ad3e64a57031
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760934"
---
# <a name="compiler-error-c2885"></a>Derleyici hatası C2885

' class:: Identifier ': sınıf olmayan kapsamda geçerli bir using bildirimi değil

[Using](../../cpp/using-declaration.md) bildirimini yanlış kullandınız.

## <a name="example"></a>Örnek

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin bir sonucu olarak oluşturulabilir: iç içe bir türe `using` bildirimine sahip olmak için artık geçerli değil; iç içe geçmiş türde yaptığınız her başvuruyu açıkça nitelemeniz, türü bir ad alanına yerleştirmeniz veya bir typedef oluşturmanız gerekir.

Aşağıdaki örnek C2885 oluşturur.

```cpp
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

Bir sınıf üyesiyle birlikte `using` anahtar sözcüğünü kullanıyorsanız, C++ bu üyeyi başka bir sınıf (türetilmiş bir sınıf) içinde tanımlamanızı gerektirir.

Aşağıdaki örnek C2885 oluşturur.

```cpp
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
