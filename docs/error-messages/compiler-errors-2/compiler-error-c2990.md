---
title: Derleyici hatası C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 1c58c2d5da0049ec670e11c930b397caec3cbbee
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751527"
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

C2990, Visual Studio için Microsoft C++ derleyicisi 2005 ' deki önemli bir değişiklik nedeniyle da oluşabilir; Derleyici artık, şablon belirtimiyle ilgili olarak aynı tür için birden çok bildirime sahip olmasını gerektirir.

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
