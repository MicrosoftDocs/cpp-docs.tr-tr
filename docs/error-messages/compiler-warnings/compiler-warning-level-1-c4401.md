---
title: Derleyici Uyarısı (düzey 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: c7e6cf8a52288d895b74481678dc91fee387a6a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455425"
---
# <a name="compiler-warning-level-1-c4401"></a>Derleyici Uyarısı (düzey 1) C4401

'bit alanı': üye bit alanıdır

Bir bit alanı üyesine erişmek satır içi derleme kodu çalışır. Bu nedenle son paket sınırında bit alanı üyesi önce kullanılır, satır içi derleme bit alanı üyeleri erişemez.

Bu uyarıyı engellemek için satır içi derleme kodunda referans yapmadan önce bit alanını uygun bir tür cast. Aşağıdaki örnek, C4401 oluşturur:

```
// C4401.cpp
// compile with: /W1
// processor: x86
typedef struct bitfield {
   signed bit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bf.bit = 0;
   __asm {
      mov bf.bit,0;   // C4401
   }

   /* use the following __asm block to resolve the warning
   int i = (int)bf.bit;
   __asm {
      mov i,0;
   }
   */
}
```