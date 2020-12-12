---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4556'
title: Derleyici Uyarısı (düzey 1) C4556
ms.date: 08/27/2018
f1_keywords:
- C4556
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
ms.openlocfilehash: a0e0780b541b74125135ab84daa6ecab80b57e83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265863"
---
# <a name="compiler-warning-level-1-c4556"></a>Derleyici Uyarısı (düzey 1) C4556

> '*Value*' iç anında bağımsız değişkeninin değeri Aralık dışında ' küçük *harfe sınırlı*  -  '

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
