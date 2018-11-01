---
title: Derleyici Hatası C3206
ms.date: 11/04/2016
f1_keywords:
- C3206
helpviewer_keywords:
- C3206
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
ms.openlocfilehash: 665244cbfc87f32274f9eaf9afacfb1caad50659
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640056"
---
# <a name="compiler-error-c3206"></a>Derleyici Hatası C3206

'function': sınıf türü 'typename' tür bağımsız değişken listesi eksik parametre','için geçersiz tür bağımsız değişkeni

Bir şablon işlevi, bir şablon türü bağımsız değişkeni alma olarak tanımlanır. Bununla birlikte, şablonu şablon bağımsız değişken geçirildi.

Aşağıdaki örnek, C3206 oluşturur:

```
// C3206.cpp
template <class T>
void f() {}

template <class T>
struct S {};

void f1() {
   f<S>();   // C3206
   // try the following line instead
   // f<S<int> >();
}
```

Olası çözüm:

```
// C3206b.cpp
// compile with: /c
template <class T>
void f() {}

template <class T>
struct S {};

void f1() {
   f<S<int> >();
}
```

C3206, genel türler kullanırken da meydana gelebilir:

```
// C3206c.cpp
// compile with: /clr
generic <class GT1>
void gf() {}

generic <class T>
value struct GS {};

int main() {
   gf<GS>();   // C3206
}
```

Olası çözüm:

```
// C3206d.cpp
// compile with: /clr
generic <class GT1>
void gf() {}

generic <class T>
value struct GS {};

int main() {
   gf<GS<int> >();
}
```

Bir sınıf şablonunun şablon türü bağımsız değişkeni izin verilmez. Aşağıdaki örnek C3206 başlatır:

```
// C3206e.cpp
template <class T>
struct S {};

template <class T>
void func() {   // takes a type
   T<int> t;
}

int main() {
   func<S>();   // C3206 S is not a type.
}
```

Olası çözüm:

```
// C3206f.cpp
template <class T>
struct S {};

template <class T>
void func() {   // takes a type
   T t;
}

int main() {
   func<S<int> >();
}
```

Şablon Şablon parametresi gerekli değilse, işlev bir şablon parametre alan bir şablon sınıfı içinde sarmalamak vardır:

```
// C3206g.cpp
template <class T>
struct S {};

template<template<class> class TT>
struct X {
   static void func() {
      TT<int> t1;
      TT<char> t2;
   }
};

int main() {
   X<S>::func();
}
```