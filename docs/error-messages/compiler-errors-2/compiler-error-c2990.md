---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2990'
title: Derleyici hatası C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 80aa15940420e9d3e452f2c3a93eefe94fd1561b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328250"
---
# <a name="compiler-error-c2990"></a>Derleyici hatası C2990

' class ': sınıf olmayan tür, zaten bir sınıf türü olarak bildirildiği için

Genel olmayan veya şablon sınıfı, genel veya şablon sınıfını tekrar tanımlar. Üst bilgi dosyalarını çakışmalar için denetleyin.

Aşağıdaki örnek C2990 oluşturur:

```cpp
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990, genel türler kullanılırken de oluşabilir:

```cpp
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990, Visual Studio 2005 için Microsoft C++ derleyicisinde önemli bir değişiklik nedeniyle da oluşabilir; Derleyici artık, şablon belirtimiyle ilgili olarak aynı tür için birden çok bildirime sahip olmasını gerektirir.

Aşağıdaki örnek C2990 oluşturur:

```cpp
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```
