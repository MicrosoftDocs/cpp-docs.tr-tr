---
title: Derleyici Uyarısı (Düzey 2) C4308
ms.date: 11/04/2016
f1_keywords:
- C4308
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
ms.openlocfilehash: f97d66f9e3445d022adc3362532774b15ea09961
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443543"
---
# <a name="compiler-warning-level-2-c4308"></a>Derleyici Uyarısı (Düzey 2) C4308

Negatif tamsayı sabiti işaretsiz türe dönüştürüldü

Bir ifade bir negatif tamsayı sabiti işaretsiz bir türe dönüştürür. İfadenin sonucu, büyük olasılıkla anlamsız olduğu.

## <a name="example"></a>Örnek

```
// C4308.cpp
// compile with: /W2
unsigned int u = (-5 + 3U);   // C4308

int main()
{
}
```