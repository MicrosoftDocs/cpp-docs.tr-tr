---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4163'
title: Derleyici Uyarısı (düzey 1) C4163
ms.date: 11/04/2016
f1_keywords:
- C4163
helpviewer_keywords:
- C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
ms.openlocfilehash: 6906b8c7926371a57ddcd6677d0c34ef57bbb383
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267124"
---
# <a name="compiler-warning-level-1-c4163"></a>Derleyici Uyarısı (düzey 1) C4163

' tanımlayıcı ': iç işlev olarak kullanılamaz

Belirtilen işlev [iç](../../preprocessor/intrinsic.md) işlev olarak kullanılamaz. Derleyici geçersiz işlev adını yok sayar.

Aşağıdaki örnek C4163 oluşturur:

```cpp
// C4163.cpp
// compile with: /W1 /LD
#include <math.h>
#pragma intrinsic(mysin)   // C4163
// try the following line instead
// #pragma intrinsic(sin)
```
