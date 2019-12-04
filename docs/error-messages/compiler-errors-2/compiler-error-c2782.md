---
title: Derleyici hatası C2782
ms.date: 11/04/2016
f1_keywords:
- C2782
helpviewer_keywords:
- C2782
ms.assetid: 8b685422-294d-4f64-9f3d-c14eaf03a93d
ms.openlocfilehash: c779a9789f532a5d623401058b9ea7e268ede17d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739733"
---
# <a name="compiler-error-c2782"></a>Derleyici hatası C2782

' declaration ': şablon parametresi ' Identifier ' belirsiz

Derleyici bir şablon bağımsız değişkeninin türünü belirleyemiyor.

Aşağıdaki örnek C2782 oluşturur:

```cpp
// C2782.cpp
template<typename T>
void f(T, T) {}

int main() {
   f(1, 'c');   // C2782
   // try the following line instead
   // f<int>(1, 'c');
}
```

C2782, genel türler kullanılırken de oluşabilir:

```cpp
// C2782b.cpp
// compile with: /clr
generic<typename T> void gf(T, T) { }

int main() {
   gf(1, 'c'); // C2782
   // try the following line instead
   // gf<int>(1, 'c');
}
```
