---
title: Derleyici Uyarısı (Düzey 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: ba6d305a414e99bd22ca603aaac2615994780c7d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185769"
---
# <a name="compiler-warning-level-1-c4730"></a>Derleyici Uyarısı (Düzey 1) C4730

' Main ': _m64 ve kayan nokta ifadelerini karıştırma hatalı koda neden olabilir

Bir işlev [__m64](../../cpp/m64.md) ve **float**/**Double** türlerini kullanır. MMX ve kayan nokta kayıtları aynı fiziksel kayıt alanını paylaştığından (aynı anda kullanılamaz), `__m64` ve **float**/aynı işlevdeki **çift** türler, veri bozulmasına neden olabilir, bu da özel duruma neden olabilir.

Aynı işlevde `__m64` türlerini ve kayan nokta türlerini güvenle kullanmak için, türlerden birini kullanan her yönerge **_m_empty ()** (MMX için) veya **_m_femms ()** (3now!) iç ile ayrılmalıdır.

Aşağıdaki örnek C4730 oluşturur:

```cpp
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```
