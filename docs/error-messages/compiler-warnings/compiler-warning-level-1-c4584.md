---
title: Derleyici Uyarısı (düzey 1) C4584
ms.date: 11/04/2016
f1_keywords:
- C4584
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
ms.openlocfilehash: fa736e8dbab775fcd6cdffc467aee1312004fa60
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162159"
---
# <a name="compiler-warning-level-1-c4584"></a>Derleyici Uyarısı (düzey 1) C4584

' Class1 ': ' Class2 ' temel sınıfı zaten bir ' Class3 ' temel sınıfı

Tanımladığınız sınıf, biri diğerinin devraldığı iki sınıftan devralır. Örneğin:

```cpp
// C4584.cpp
// compile with: /W1 /LD
class A {
};

class B : public A {
};

class C : public A, public B { // C4584
};
```

Bu durumda C sınıfında bir uyarı verilir çünkü hem sınıf A 'dan hem de B sınıfından devralır. Bu uyarı, bu temel sınıflardan üyelerin kullanımını tam olarak nitelemeniz gerektiğini belirten bir anımsatıcı görevi görür veya hangi sınıf üyesine başvurabileceğiniz belirsizlik nedeniyle bir derleyici hatası oluşturulur.
