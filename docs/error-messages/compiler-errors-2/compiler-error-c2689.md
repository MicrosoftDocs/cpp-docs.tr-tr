---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2689'
title: Derleyici hatası C2689
ms.date: 11/04/2016
f1_keywords:
- C2689
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
ms.openlocfilehash: 532db26a3c0da3191c9b15215d470618e561e76a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326720"
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
