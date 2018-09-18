---
title: Derleyici Hatası C2885 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2885
dev_langs:
- C++
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf47d830980b9fb93481f575e3e3a806ce8bbf68
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035701"
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