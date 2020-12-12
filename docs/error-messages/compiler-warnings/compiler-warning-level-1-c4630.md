---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4630'
title: Derleyici Uyarısı (düzey 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 49a73dcd3ce11fefa1d4275e57ad98092c242d8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318916"
---
# <a name="compiler-warning-level-1-c4630"></a>Derleyici Uyarısı (düzey 1) C4630

' symbol ': ' extern ' depolama sınıfı belirticisi üye tanımında geçersizdir

Bir veri üyesi veya üye işlevi olarak tanımlanır **`extern`** . Tüm nesneler içerebilse de Üyeler dış olamaz. Derleyici **`extern`** anahtar sözcüğünü yoksayar. Aşağıdaki örnek C4630 oluşturur:

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
