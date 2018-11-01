---
title: Derleyici Hatası C2910
ms.date: 11/04/2016
f1_keywords:
- C2910
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
ms.openlocfilehash: 58d56ad834b34425cda4ac7ba081eabd2424e451
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547270"
---
# <a name="compiler-error-c2910"></a>Derleyici Hatası C2910

'function': açıkça özelleştirilemez

Derleyici bir işlevi açıkça iki kez specialize girişimi algıladı.

Aşağıdaki örnek, C2910 oluşturur:

```
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

Şablon olmayan üye açıkça specialize çalışırsanız C2910 de meydana gelebilir. Diğer bir deyişle, bir işlev şablonu yalnızca açıkça uzmanlaşmıştır.

Aşağıdaki örnek, C2910 oluşturur:

```
// C2910b.cpp
// compile with: /c
template <class T> struct A {
   A(T* p);
};

template <> struct A<void> {
   A(void* p);
};

template <class T>
inline A<T>::A(T* p) {}

template <> A<void>::A(void* p){}   // C2910
// try the following line instead
// A<void>::A(void* p){}
```

Bu hata ayrıca Visual Studio .NET 2003'te yapıldığı derleyici uyumluluğu iş sonucu olarak oluşturulacak:.

Kodu Visual C++ Visual Studio .NET 2003 ve Visual Studio sürümlerinde geçerli olacaktır, kaldırma `template <>`.

Aşağıdaki örnek, C2910 oluşturur:

```
// C2910c.cpp
// compile with: /c
template <class T> class A {
   void f();
};

template <> class A<int> {
   void f();
};

template <> void A<int>::f() {}   // C2910
// try the following line instead
// void A<int>::f(){}   // OK
```