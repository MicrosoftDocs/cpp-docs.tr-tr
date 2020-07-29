---
title: Derleyici hatası C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 9b6b7bb54d5dce48dc6fce517eb0c909b0284da2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233450"
---
# <a name="compiler-error-c2885"></a>Derleyici hatası C2885

' class:: Identifier ': sınıf olmayan kapsamda geçerli bir using bildirimi değil

[Using](../../cpp/using-declaration.md) bildirimini yanlış kullandınız.

## <a name="example"></a>Örnek

Bu hata, Visual Studio 2005 için yapılan derleyici uyumluluğu işinin bir sonucu olarak oluşturulabilir: iç içe bir türe yönelik bir bildirime sahip olmak için artık geçerli değil **`using`** ; iç içe geçmiş türde yaptığınız her başvuruyu açıkça nitelemeniz, türü bir ad alanına koymanız veya bir typedef oluşturmanız gerekir.

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
