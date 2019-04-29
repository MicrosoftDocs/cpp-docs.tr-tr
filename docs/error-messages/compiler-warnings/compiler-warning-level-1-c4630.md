---
title: Derleyici Uyarısı (düzey 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 98ea72bef0cb95163604144c1069a13c3b27d81c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324538"
---
# <a name="compiler-warning-level-1-c4630"></a>Derleyici Uyarısı (düzey 1) C4630

'symbol': 'extern' depolama sınıfı belirticisi üye tanımında geçersizdir

Bir veri üyesine veya üye işlevi olarak tanımlanır `extern`. Tüm nesneler, ancak üye harici olamaz. Derleyicinin yoksaydığı `extern` anahtar sözcüğü. Aşağıdaki örnek, C4630 oluşturur:

```
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```