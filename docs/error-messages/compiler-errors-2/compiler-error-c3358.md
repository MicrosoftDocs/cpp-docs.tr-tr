---
title: Derleyici hatası C3358
ms.date: 11/04/2016
f1_keywords:
- C3358
helpviewer_keywords:
- C3358
ms.assetid: 180b93df-e78f-441a-91fb-1594c681f7f0
ms.openlocfilehash: 64b966ff674b10fd7df99e5a04a9b16d21d89b96
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759769"
---
# <a name="compiler-error-c3358"></a>Derleyici hatası C3358

' symbol ': simge bulunamadı

Gerekli simge bulunamadı.

Aşağıdaki örnek C3358 oluşturur:

```cpp
// C3358.cpp
#define __ATLEVENT_H__ 1   // remove this line to resolve the error
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[event_receiver(com)]
struct A   // C3358
{
   void func();
};

int main()
{
}
```
