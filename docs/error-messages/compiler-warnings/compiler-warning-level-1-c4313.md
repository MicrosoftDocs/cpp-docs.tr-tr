---
title: Derleyici Uyarısı (düzey 1) C4313
ms.date: 11/04/2016
f1_keywords:
- C4313
helpviewer_keywords:
- C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
ms.openlocfilehash: 774af2d5d29112d56adf97e22d1bdd758a816ef1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555716"
---
# <a name="compiler-warning-level-1-c4313"></a>Derleyici Uyarısı (düzey 1) C4313

'function': 'type' dize bağımsız değişken sayısı ve türü ile çakışıyor 'biçiminde biçim belirticisi'

Belirtilen biçim ile geçirdiğiniz değer arasında bir çakışma var. Örneğin, 32-bit tamsayı parametre bekliyor bir nitelenmemiş %d biçim tanımlayıcısı için bir 64-bit parametresi geçirildi. 64-bit hedefleri için derlenen kod bu uyarıyı yalnızca etkilidir.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir 64 bit hedef için derlendiğinde C4313 oluşturur.

```
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