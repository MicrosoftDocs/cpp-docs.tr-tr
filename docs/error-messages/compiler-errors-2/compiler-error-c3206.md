---
title: Derleyici hatası C3206
ms.date: 11/04/2016
f1_keywords:
- C3206
helpviewer_keywords:
- C3206
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
ms.openlocfilehash: 7a602238ca5a2f2a64eaa601cc6733a897b9fdb4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738693"
---
# <a name="compiler-error-c3206"></a>Derleyici hatası C3206

' function ': ' param ' için geçersiz tür bağımsız değişkeni, ' TypeName ' sınıf türünde tür bağımsız değişken listesi eksik

Şablon işlevi bir şablon türü bağımsız değişkeni alınarak tanımlanır. Ancak, bir şablon şablonu bağımsız değişkeni geçildi.

Aşağıdaki örnek C3206 oluşturur:

```cpp
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

```cpp
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

C3206, genel türler kullanılırken de oluşabilir:

```cpp
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

```cpp
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

Bir sınıf şablonuna şablon türü bağımsız değişkeni olarak izin verilmez. Aşağıdaki örnek C3206 yükseltilir:

```cpp
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

```cpp
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

Bir şablon şablon parametresi gerekliyse, işlevi bir şablon şablon parametresi alan bir şablon sınıfında sarmalıdır:

```cpp
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
