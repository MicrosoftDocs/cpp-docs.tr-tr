---
title: Derleyici Hatası C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 16c111a0fb8608615abaee495680fa38920b6c77
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447350"
---
# <a name="compiler-error-c2990"></a>Derleyici Hatası C2990

'class': sınıf olmayan türü olarak zaten bir sınıf türü olarak bildirilmiş

Olmayan genel veya Şablon sınıfı bir genel veya Şablon sınıfı yeniden tanımlar. Çakışmaları için üst bilgi dosyaları denetleyin.

Aşağıdaki örnek, C2990 oluşturur:

```
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990, genel türler kullanırken da meydana gelebilir:

```
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990 Microsoft bir değişiklik nedeniyle de oluşabilir C++ Visual Studio 2005; derleyici Derleyici, şimdi aynı türü için birden fazla bildirimi şablonu belirtimine göre aynı olmasını gerektirir.

Aşağıdaki örnek, C2990 oluşturur:

```
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