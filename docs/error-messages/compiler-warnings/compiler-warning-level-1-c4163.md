---
title: Derleyici Uyarısı (düzey 1) C4163
ms.date: 11/04/2016
f1_keywords:
- C4163
helpviewer_keywords:
- C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
ms.openlocfilehash: 737cf7ad00bfefd429792eed3f730844789e0c02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597177"
---
# <a name="compiler-warning-level-1-c4163"></a>Derleyici Uyarısı (düzey 1) C4163

'identifier': iç işlev olarak kullanılamaz

Belirtilen işlev olarak kullanılamaz bir [iç](../../preprocessor/intrinsic.md) işlevi. Derleyici, geçersiz işlev adı yok sayar.

Aşağıdaki örnek, C4163 oluşturur:

```
// C4163.cpp
// compile with: /W1 /LD
#include <math.h>
#pragma intrinsic(mysin)   // C4163
// try the following line instead
// #pragma intrinsic(sin)
```