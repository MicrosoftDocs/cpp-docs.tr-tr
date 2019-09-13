---
title: Derleyici Uyarısı (düzey 1) C4319
ms.date: 01/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: 2d5ae8fcf5a527031c3a974b227f713675f31ffa
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926109"
---
# <a name="compiler-warning-level-1-c4319"></a>Derleyici Uyarısı (düzey 1) C4319

> ' ~ ': '*Type1*' değerini daha büyük boyuttaki '*type2*' öğesine genişletme

**~** (Bit düzeyinde tamamlama) işlecinin sonucu işaretsiz olur ve daha büyük bir türe dönüştürüldüğünde sıfır genişletilir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, `~(a - 1)` 32 bitlik bir işaretsiz Long ifadesi olarak değerlendirilir ve ardından sıfır uzantısına göre 64 bite dönüştürülür. Bu beklenmeyen işlem sonuçlarına yol açabilir.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
