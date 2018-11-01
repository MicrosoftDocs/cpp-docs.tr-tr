---
title: Derleyici Uyarısı (Düzey 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: 4da60194deaeac3c79f8c3e9be3bd87d91bc7ca2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487041"
---
# <a name="compiler-warning-level-1-c4730"></a>Derleyici Uyarısı (Düzey 1) C4730

'main': mixing _m64 ve kayan nokta ifadeleri hatalı koda neden olabilir

Bir işlev kullanan [__m64](../../cpp/m64.md) ve **float**/**çift** türleri. Kayıt alanı MMX ve kayan nokta kayıtlarını aynı fiziksel paylaştığından (aynı anda kullanarak kullanılamaz) `__m64` ve **float**/**çift** aynı türleri işlevi, büyük olasılıkla bir özel duruma neden veri bozulmasına neden olabilir.

Güvenli bir şekilde kullanmak için `__m64` türleri ve kayan nokta türleri aynı işlevde, türlerinden birini kullanan her yönerge ayrılmalıdır **_m_empty()** (için MMX) veya **_m_femms()** (için 3DNow!) İç.

Aşağıdaki örnek, C4730 oluşturur:

```
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