---
title: Derleyici Uyarısı (düzey 1) C4683
ms.date: 08/27/2018
f1_keywords:
- C4683
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
ms.openlocfilehash: f86cf8f6d894d6efaa1b49977634956dc1979a98
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175435"
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
