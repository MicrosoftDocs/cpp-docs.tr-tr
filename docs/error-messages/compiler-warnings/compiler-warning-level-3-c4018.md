---
title: Derleyici Uyarısı (Düzey 3) C4018
ms.date: 11/04/2016
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
ms.openlocfilehash: 6436f62a06cbe931ca5b42751d60507f21675c5c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556552"
---
# <a name="compiler-warning-level-3-c4018"></a>Derleyici Uyarısı (Düzey 3) C4018

'expression': imzalı/imzasız uyuşmazlığı

İşaretli ve işaretsiz sayı karşılaştırma derleyici, işaretli değeri işaretsiz dönüştürmek için gereklidir.

Bu uyarı, iki tür imzalı ve imzasız türler test ederken cast düzeltilebilir.

Aşağıdaki örnek, C4018 oluşturur:

```
// C4018.cpp
// compile with: /W3
int main() {
   unsigned int uc = 0;
   int c = 0;
   unsigned int c2 = 0;

   if (uc < c) uc = 0;   // C4018

   // OK
   if (uc == c2) uc = 0;
}
```