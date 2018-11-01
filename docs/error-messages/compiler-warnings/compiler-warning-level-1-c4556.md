---
title: Derleyici Uyarısı (düzey 1) C4556
ms.date: 08/27/2018
f1_keywords:
- xml
- C4556
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
ms.openlocfilehash: 53261b97249340ce56ce6ae0f5cc0eab7e97a107
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538495"
---
# <a name="compiler-warning-level-1-c4556"></a>Derleyici Uyarısı (düzey 1) C4556

> İç ilk bağımsız değişkeninin değeri '*değer*' je mimo rozsah'*lowerbound* - *upperbound*'

## <a name="remarks"></a>Açıklamalar

Bir iç donanım yönerge eşleşir. Donanım yönerge sabit kodlamak için BITS sabit sayıda sahiptir. Varsa *değer* olan aralık dışında bu düzgün kodlar değil. Derleyici, ekstra bit keser.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4556 oluşturur:

```cpp
// C4556.cpp
// compile with: /W1
// processor: x86 IPF
#include <xmmintrin.h>

void test()
{
   __m64 m;
   _m_pextrw(m, 5);   // C4556
}

int main()
{
}
```