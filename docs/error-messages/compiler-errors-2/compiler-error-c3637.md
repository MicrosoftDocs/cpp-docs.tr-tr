---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3637'
title: Derleyici hatası C3637
ms.date: 11/04/2016
f1_keywords:
- C3637
helpviewer_keywords:
- C3637
ms.assetid: 72391377-8519-43d9-870a-73a6423deb74
ms.openlocfilehash: d62612778690984245d6b90fc1449177ec5f8d2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239213"
---
# <a name="compiler-error-c3637"></a>Derleyici hatası C3637

' function ': bir arkadaş işlev tanımı bir işlev türünün özelleştirmesi olamaz

Bir Friend işlevi bir şablon veya genel için yanlış tanımlanmış.

Aşağıdaki örnek C3637 oluşturur:

```cpp
// C3637.cpp
template <class T>
void f();

struct S {
   friend void f<int>() {}   // C3637
};
```

Olası çözüm:

```cpp
// C3637b.cpp
// compile with: /c
template <class T>
void f();

struct S {
   friend void f() {}
};
```

C3637, genel türler kullanılırken de oluşabilir:

```cpp
// C3637c.cpp
// compile with: /clr

generic <class T>
void gf();

struct S {
   friend void gf<int>() {}   // C3637
};
```

Olası çözüm:

```cpp
// C3637d.cpp
// compile with: /clr /c
generic <class T>
void gf();

struct S {
   friend void gf() {}
};
```
