---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2885'
title: Derleyici hatası C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 040f7a151c34fe7b5e30b6aad1e5bc956b3e5cf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337490"
---
# <a name="compiler-error-c2885"></a>Derleyici hatası C2885

' class:: Identifier ': sınıf olmayan kapsamda geçerli bir using bildirimi değil

[Using](../../cpp/using-declaration.md) bildirimini yanlış kullandınız.

Bu hata, Visual Studio 2005 için yapılan derleyici uyumluluğu işinin bir sonucu olarak oluşturulabilir: iç içe bir türe yönelik bir bildirime sahip olmak için artık geçerli değil **`using`** ; iç içe geçmiş türde yaptığınız her başvuruyu açıkça nitelemeniz, türü bir ad alanına koymanız veya bir typedef oluşturmanız gerekir.

## <a name="examples"></a>Örnekler

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

**`using`** Anahtar sözcüğünü bir sınıf üyesiyle birlikte kullanırsanız, C++ bu üyeyi başka bir sınıf (türetilmiş bir sınıf) içinde tanımlamanızı gerektirir.

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
