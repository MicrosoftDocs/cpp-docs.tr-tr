---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4584'
title: Derleyici Uyarısı (düzey 1) C4584
ms.date: 11/04/2016
f1_keywords:
- C4584
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
ms.openlocfilehash: 32a6b797f7fb0cf2c1a087999c8172e11686e27b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281632"
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
