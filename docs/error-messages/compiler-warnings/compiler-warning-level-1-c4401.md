---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4401'
title: Derleyici Uyarısı (düzey 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: c6314b64ef9a675f8838cc7c3f4c89c2d6063231
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212746"
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
