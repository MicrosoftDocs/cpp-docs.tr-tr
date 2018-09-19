---
title: Derleyici Uyarısı (düzey 4) C4937 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4937
dev_langs:
- C++
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7bc6232458b357f41e859c58d4b6b77f78ef2a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118303"
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