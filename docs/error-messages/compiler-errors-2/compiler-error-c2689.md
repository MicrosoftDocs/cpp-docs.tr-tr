---
title: Derleyici Hatası C2689
ms.date: 11/04/2016
f1_keywords:
- C2689
helpviewer_keywords:
- C2689
ms.assetid: b5216fba-524d-4194-9168-26e9dc5210ce
ms.openlocfilehash: fb9a45f775da582daa0fbe421f29b6e469a91197
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266016"
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