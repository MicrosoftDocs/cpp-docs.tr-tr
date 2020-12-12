---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3463'
title: Derleyici hatası C3463
ms.date: 11/04/2016
f1_keywords:
- C3463
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
ms.openlocfilehash: 4d208780deb8e2cba738aec7a5ddf1b5df93f300
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113498"
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
