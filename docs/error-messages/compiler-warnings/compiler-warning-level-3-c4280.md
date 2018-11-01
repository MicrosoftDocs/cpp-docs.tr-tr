---
title: Derleyici Uyarısı (Düzey 3) C4280
ms.date: 11/04/2016
f1_keywords:
- C4280
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
ms.openlocfilehash: 6a3daa9903cbf983ddc19538a154d9717a2f9f0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618939"
---
# <a name="compiler-warning-level-3-c4280"></a>Derleyici Uyarısı (Düzey 3) C4280

'operator ->' kendi kendine özniyeleniyordu türü aracılığıyla 'type'

Kodunuzun yanlış sağlar **-> işleci** kendisini çağırmak için.

Aşağıdaki örnek, C4280 oluşturur:

```
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```