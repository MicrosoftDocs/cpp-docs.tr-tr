---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4319'
title: Derleyici Uyarısı (düzey 1) C4319
ms.date: 01/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: af38714ab506fad389d9d2407b5a83aebf01f7c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340066"
---
# <a name="compiler-warning-level-1-c4319"></a>Derleyici Uyarısı (düzey 1) C4319

> ' ~ ': '*Type1*' değerini daha büyük boyuttaki '*type2*' öğesine genişletme

**~**(Bit düzeyinde tamamlama) işlecinin sonucu işaretsiz olur ve daha büyük bir türe dönüştürüldüğünde sıfır genişletilir.

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
