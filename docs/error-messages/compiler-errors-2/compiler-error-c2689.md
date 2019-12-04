---
title: Derleyici hatası C2689
ms.date: 11/04/2016
f1_keywords:
- C2689
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
ms.openlocfilehash: f3b35d8f68087c9f10d7f2a5d219800fc7a9084a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760234"
---
# <a name="compiler-error-c2689"></a>Derleyici hatası C2689

' function ': bir arkadaş işlev bir yerel sınıf içinde tanımlanamaz

Bir yerel sınıfta arkadaş işlevi tanımlayabilir ancak tanımlayamazsınız.

Aşağıdaki örnek C2689 oluşturur:

```cpp
// C2689.cpp
// compile with: /c
void g() {
   void f2();
   class X {
      friend void f2(){}   // C2689
      friend void f2();   // OK
   };
}
```
