---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4730'
title: Derleyici Uyarısı (Düzey 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: e026d44bc76d58c934eeccc363f4385f43d15597
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150663"
---
# <a name="compiler-warning-level-1-c4730"></a>Derleyici Uyarısı (Düzey 1) C4730

' Main ': _m64 ve kayan nokta ifadelerini karıştırma hatalı koda neden olabilir

Bir işlev [__m64](../../cpp/m64.md) ve **`float`** / **`double`** türlerini kullanır. MMX ve kayan nokta kayıtları aynı fiziksel kayıt alanını paylaştığından (aynı anda kullanılamaz), **`__m64`** **`float`** / **`double`** aynı işlevde kullanılması ve türleri veri bozulmasına neden olabilir, bu da özel durum olabilir.

**`__m64`** Aynı işlevde türleri ve kayan nokta türlerini güvenle kullanmak için, türlerden birini kullanan her yönerge **_m_empty ()** (MMX için) veya **_M_femms ()** (3now!) iç ile ayrılmalıdır.

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
