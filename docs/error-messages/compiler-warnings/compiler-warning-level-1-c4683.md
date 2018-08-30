---
title: Derleyici Uyarısı (düzey 1) C4683 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a157d3beb7c2efa7f1144a961973652e2ce384f7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194203"
---
# <a name="compiler-warning-level-1-c4683"></a>Derleyici Uyarısı (düzey 1) C4683

> '*işlevi*': olay kaynağı olan bir 'out'-parametre; birden çok olay işleyicisi yakalarken dikkatli olun

## <a name="remarks"></a>Açıklamalar

Birden fazla olay havuz bir COM Olay kaynağına dinliyorsa, out parametresi değerini yoksayılabilir.

Bir bellek sızıntısı aşağıdaki durumlarda oluşur dikkat edin:

1. Bir yöntemi dahili olarak, örneğin bir BSTR ayrılan out parametresi varsa *.

2. Olay işleyicisine birden fazla varsa (bir çok noktaya yayın olay değer).

Out parametresi birden fazla işleyici tarafından ayarlanmış, ancak çağrı sitesine yalnızca son işleyici tarafından döndürülen, sızıntı nedeni.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4683 oluşturur ve bu sorunun nasıl gösterir:

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