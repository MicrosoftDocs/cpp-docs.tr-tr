---
title: Derleyici hatası C3463
ms.date: 11/04/2016
f1_keywords:
- C3463
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
ms.openlocfilehash: e4aa8405d9baac61b8d3addead6ac19bbf6fd3b0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756597"
---
# <a name="compiler-error-c3463"></a>Derleyici hatası C3463

' Type ': türe ' Implements ' özniteliğinde izin verilmiyor

[Implements](../../windows/implements-cpp.md) özniteliğine geçersiz bir tür geçirildi. Örneğin, `implements`bir arabirim geçirebilirsiniz, ancak bir arabirime işaretçi geçirilemez.

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
