---
title: Derleyici Uyarısı (düzey 1) C4556
ms.date: 08/27/2018
f1_keywords:
- C4556
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
ms.openlocfilehash: 501d79a8a86fcd3e2d8ba08dc2f03488f9abb827
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162315"
---
# <a name="compiler-warning-level-1-c4556"></a>Derleyici Uyarısı (düzey 1) C4556

> iç ilk bağımsız değişken '*Value*' değeri Aralık dışında '*albağı* - üst *sınırı*'

## <a name="remarks"></a>Açıklamalar

Bir iç donanım yönergesiyle eşleşir. Donanım yönergesinde sabit değer kodlamak için sabit sayıda bit vardır. *Değer* Aralık dışında değilse, doğru şekilde kodlanmaz. Derleyici ek bitleri keser.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4556 oluşturur:

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
