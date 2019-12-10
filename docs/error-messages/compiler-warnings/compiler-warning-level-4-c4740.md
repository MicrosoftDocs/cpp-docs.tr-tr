---
title: Derleyici Uyarısı (düzey 4) C4740
ms.date: 11/04/2016
f1_keywords:
- C4740
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
ms.openlocfilehash: 679f577eb7911b401473ee570e367ed5a8a094eb
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74989482"
---
# <a name="compiler-warning-level-4-c4740"></a>Derleyici Uyarısı (düzey 4) C4740

satır içi asm kodunun içinde veya dışında akışı genel iyileştirme 'yi gizler

`asm` bloğunun içine veya dışına bir geçiş yapıldığında, bu işlev için genel iyileştirmeler devre dışı bırakılır.

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
