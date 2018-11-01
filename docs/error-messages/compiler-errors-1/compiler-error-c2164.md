---
title: Derleyici Hatası C2164
ms.date: 11/04/2016
f1_keywords:
- C2164
helpviewer_keywords:
- C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
ms.openlocfilehash: 3b1c7a94dfca1c2767e14f96204ecda670c8a586
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460820"
---
# <a name="compiler-error-c2164"></a>Derleyici Hatası C2164

'function': iç işlevin bildirimi yapılmadı

Bir `intrinsic` pragma bildirilmemiş bir işlevi kullanır (yalnızca oluşur **/Oi**). Veya, derleyici iç bilgileri birini kendi üst bilgi dosyasını dahil olmak üzere kullanılmıştır.

Aşağıdaki örnek, C2164 oluşturur:

```
// C2164.c
// compile with: /c
// processor: x86
// Uncomment the following line to resolve.
// #include "xmmintrin.h"
void b(float *p) {
   _mm_load_ss(p);   // C2164
}
```