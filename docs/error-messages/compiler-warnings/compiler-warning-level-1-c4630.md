---
title: Derleyici Uyarısı (düzey 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 414388fc1b9c6a7425d45e2ba92546960cadf404
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199621"
---
# <a name="compiler-warning-level-1-c4630"></a>Derleyici Uyarısı (düzey 1) C4630

' symbol ': ' extern ' depolama sınıfı belirticisi üye tanımında geçersizdir

Bir veri üyesi veya üye işlevi `extern`olarak tanımlanır. Tüm nesneler içerebilse de Üyeler dış olamaz. Derleyici `extern` anahtar sözcüğünü yok sayar. Aşağıdaki örnek C4630 oluşturur:

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
