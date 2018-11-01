---
title: Derleyici Uyarısı (Düzey 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: 55512bf28c8c20512d0d245810d3e5c1fec36939
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600700"
---
# <a name="compiler-warning-level-3-c4334"></a>Derleyici Uyarısı (Düzey 3) C4334

'operator': 32-bit kaydırmanın sonucu örtük olarak 64 bite dönüştürüldü (64-bit kaydırmanın hedeflenen oldu mu?)

32-bit kaydırmanın sonucu örtük olarak 64-bit ve 64-bit kaydırmanın tasarlanmıştı derleyici şüphelerini dönüştürüldü.  Bu uyarıyı çözmek için 64-bit kaydırmanın kullanabilir veya 64-bit kaydırma sonucu açıkça dönüştürün.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4334 oluşturur.

```
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```