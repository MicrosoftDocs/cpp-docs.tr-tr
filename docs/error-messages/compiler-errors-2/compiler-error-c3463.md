---
title: Derleyici Hatası C3463
ms.date: 11/04/2016
f1_keywords:
- C3463
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
ms.openlocfilehash: a0c7772291085bcd872cbc1ca23b79d2fa829ad9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448678"
---
# <a name="compiler-error-c3463"></a>Derleyici Hatası C3463

'type': türe 'implements' özniteliğinin içinde izin verilmiyor

Geçersiz bir tür geçildi [uygulayan](../../windows/implements-cpp.md) özniteliği. Örneğin, bir arabirim geçirebilirsiniz `implements`, ancak bir arabirim işaretçisi geçiremezsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3463 oluşturur.

```
// C3463.cpp
// compile with: /c
#include <windows.h>
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface X {};

typedef X* PX;

[ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=PX) ]   // C3463
// try the following line instead
// [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=X) ]
class CMyClass : public X {};
```