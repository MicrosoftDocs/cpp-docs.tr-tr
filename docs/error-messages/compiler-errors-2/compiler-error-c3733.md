---
title: Derleyici Hatası C3733
ms.date: 11/04/2016
f1_keywords:
- C3733
helpviewer_keywords:
- C3733
ms.assetid: 0cc1a9fe-1400-4be3-b35a-16435cba7a5a
ms.openlocfilehash: 006f87691c6e0839115e2c02ab0d922aa95eaa93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327983"
---
# <a name="compiler-error-c3733"></a>Derleyici Hatası C3733

'event': bir COM olayı belirtmek için hatalı sözdizimi '__interface' belirtmeyi unuttunuz?

Bir COM olay için hatalı sözdizimi kullanıldı. Bu hatayı düzeltmek için olay türünü değiştirin veya COM olay kurallarına uygun söz dizimini düzeltin.

Aşağıdaki örnek, C3733 oluşturur:

```
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[coclass, event_source(com), // change 'com' to 'native' to resolve
uuid("00000000-0000-0000-0000-000000000001")]
class A
{
   __event void func();   // C3733
};

int main()
{
}
```