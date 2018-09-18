---
title: Derleyici Hatası C3463 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3463
dev_langs:
- C++
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2169897a3ad4a6d2d78f22b7ea323d70020e1b12
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036624"
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