---
title: Derleyici Uyarısı (düzey 1) C4313
ms.date: 11/04/2016
f1_keywords:
- C4313
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
ms.openlocfilehash: 4000ba2254c868bf9959a6f0fb6f8e76255f7590
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966075"
---
# <a name="compiler-warning-level-1-c4313"></a>Derleyici Uyarısı (düzey 1) C4313

' function ': biçim dizesindeki ' Biçim belirleyicisi ', ' Type ' türündeki bağımsız değişken sayısıyla çakışıyor

Belirtilen biçim ve geçirdiğiniz değer arasında bir çakışma var. Örneğin, 64 bitlik bir parametreyi, bir 32 bit tamsayı parametresi bekleyen, tam olmayan bir% d biçim tanımlayıcısına geçirtiniz. Bu uyarı yalnızca kod 64-bit hedefler için derlenmişse geçerlidir.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, 64 bitlik bir hedef için derlendiğinde C4313 oluşturur.

```cpp
// C4313.cpp
// Compile by using: cl /W1 C4313.cpp
#include <stdio.h>
int main() {
   int * pI = 0;
   printf("%d", pI);   // C4313 on 64-bit platform code
   // Try one of the following lines instead:
   // printf("%p\n", pI);
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information
}
```