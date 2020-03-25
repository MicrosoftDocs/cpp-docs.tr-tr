---
title: Derleyici Uyarısı (düzey 1) C4313
ms.date: 11/04/2016
f1_keywords:
- C4313
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
ms.openlocfilehash: 14ac938d62b4c5b6f22957268721aea9c3ffef22
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163056"
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
