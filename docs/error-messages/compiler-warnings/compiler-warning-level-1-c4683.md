---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4683'
title: Derleyici Uyarısı (düzey 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: e7f2c76e7f15bb7342e60b2aa390cf0bd1a8ce05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285246"
---
# <a name="compiler-warning-level-1-c4683"></a>Derleyici Uyarısı (düzey 1) C4683

> '*Function*': olay kaynağında ' out' parametresi vardır; birden çok olay işleyicisini gönderirken dikkatli olun

## <a name="remarks"></a>Açıklamalar

Birden fazla olay havuzu bir COM olay kaynağını dinliyorsa, bir out parametresinin değeri yoksayılabilir.

Aşağıdaki durumlarda bir bellek sızıntısı oluşması gerektiğini unutmayın:

1. Bir yöntemde iç ayrılmış bir out parametresi varsa, örneğin bir BSTR *.

2. Olayda birden fazla işleyici varsa (çok noktaya yayın olayıdır).

Sızıntı nedeni Out parametresinin birden fazla işleyici tarafından ayarlanmasının, ancak yalnızca son işleyicinin çağrı sitesine döndürüldüğünden olur.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4683 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```
