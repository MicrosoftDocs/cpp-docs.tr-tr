---
title: Derleyici Uyarısı (düzey 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: fe08509a05eed00f7e7d492e723e873d05e451ad
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162666"
---
# <a name="compiler-warning-level-1-c4401"></a>Derleyici Uyarısı (düzey 1) C4401

' bitfield ': üye bit alanıdır

Satır içi derleme kodu bir bit alanı üyesine erişmeye çalışır. Satır içi bütünleştirilmiş kod, bit alan üyelerine erişemez, bu nedenle, bit alanı üyesi kullanılmadan önce son paketleme sınırı kullanılır.

Bu uyarıyı önlemek için, satır içi derleme kodunda başvuruyu yapmadan önce bit alanını uygun bir türe atayın. Aşağıdaki örnek C4401 oluşturur:

```cpp
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
