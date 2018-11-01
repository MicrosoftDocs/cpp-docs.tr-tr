---
title: Derleyici Hatası C2689
ms.date: 11/04/2016
f1_keywords:
- C2689
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
ms.openlocfilehash: fb9a45f775da582daa0fbe421f29b6e469a91197
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484558"
---
# <a name="compiler-error-c2689"></a>Derleyici Hatası C2689

'function': bir arkadaş işlev bir yerel sınıf içinde tanımlanamaz

Bildirmesine rağmen bir arkadaş işlev bir yerel sınıf içinde tanımlayın değil.

Aşağıdaki örnek, C2689 oluşturur:

```
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