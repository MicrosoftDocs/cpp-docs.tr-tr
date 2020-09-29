---
title: Derleyici hatası C3463
ms.date: 11/04/2016
f1_keywords:
- C3463
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
ms.openlocfilehash: 29b30f5d518b6b6df768693666ea1af1c515c540
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500471"
---
# <a name="compiler-error-c3463"></a>Derleyici hatası C3463

' Type ': türe ' Implements ' özniteliğinde izin verilmiyor

[Implements](../../windows/attributes/implements-cpp.md) özniteliğine geçersiz bir tür geçirildi. Örneğin, arabirimine bir arabirim geçirebilirsiniz `implements` , ancak bir arabirime işaretçi geçirilemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3463 oluşturur.

```cpp
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
