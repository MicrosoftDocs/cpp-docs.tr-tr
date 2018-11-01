---
title: Derleyici Uyarısı (düzey 4) C4937
ms.date: 11/04/2016
f1_keywords:
- C4937
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
ms.openlocfilehash: 64565ad37c965aa0af3b912988586b37270be6a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548762"
---
# <a name="compiler-warning-level-4-c4937"></a>Derleyici Uyarısı (düzey 4) C4937

'text1' ve 'text2' 'yönergesi' için bağımsız değişkenler olarak ayırt edilemiyor

Şekli nedeniyle derleyici yönergeleri, derleyici için birden çok metin temsilleridir (tek veya çift alt çizgi formlar) anahtar sözcükler gibi bir anlamı yoktur, ayırt edici olamaz adları bağımsız işler.

Bu tür dize örnekleridir __cdecl ve \__forceinline.  , /Za altında yalnızca çift alt çizgi formları etkin unutmayın.

Aşağıdaki örnek, C4937 oluşturur:

```
// C4937.cpp
// compile with: /openmp /W4
#include "omp.h"
int main() {
   #pragma omp critical ( __leave )   // C4937
   ;

   // OK
   #pragma omp critical ( leave )
   ;
}
```