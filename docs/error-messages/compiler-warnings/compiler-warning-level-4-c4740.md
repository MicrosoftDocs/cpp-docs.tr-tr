---
title: Derleyici Uyarısı (düzey 4) C4740
ms.date: 11/04/2016
f1_keywords:
- C4740
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
ms.openlocfilehash: 936dfb5464eabe7b1ac44df24445224fb9e204a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187036"
---
# <a name="compiler-warning-level-4-c4740"></a>Derleyici Uyarısı (düzey 4) C4740

veya satır içi asm kodunda dışarı akma, genel iyileştirmeyi bastırır

Olduğunda bir atlama içinde veya dışında bir `asm` blok, bu işlev için genel iyileştirmeler devre dışı.

Aşağıdaki örnek, C4740 oluşturur:

```
// C4740.cpp
// compile with: /O2 /W4
// processor: x86
int main() {
   __asm jmp tester
   tester:;
}
```