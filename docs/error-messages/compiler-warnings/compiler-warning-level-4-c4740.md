---
title: Derleyici Uyarısı (düzey 4) C4740
ms.date: 11/04/2016
f1_keywords:
- C4740
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
ms.openlocfilehash: 0aa4cb9df3f6f9d7499c67fb0b07bee5dabd6d73
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219839"
---
# <a name="compiler-warning-level-4-c4740"></a>Derleyici Uyarısı (düzey 4) C4740

satır içi asm kodunun içinde veya dışında akışı genel iyileştirme 'yi gizler

Bir blok içine veya dışına geçiş yapıldığında **`asm`** , bu işlev için genel iyileştirmeler devre dışı bırakılır.

Aşağıdaki örnek C4740 oluşturur:

```cpp
// C4740.cpp
// compile with: /O2 /W4
// processor: x86
int main() {
   __asm jmp tester
   tester:;
}
```
