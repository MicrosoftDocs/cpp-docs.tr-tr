---
title: Derleyici Hatası C2013
ms.date: 11/04/2016
f1_keywords:
- C2013
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
ms.openlocfilehash: b279202b8b32197a99d230040207aa50bc100495
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618484"
---
# <a name="compiler-error-c2013"></a>Derleyici Hatası C2013

eksik ' >'

Bir `#include` yönergesi bir kapanış açılı ayracı eksik. Hatayı gidermek için sol ayraç ekleyin.

Aşağıdaki örnek, C2013 oluşturur:

```
// C2013.cpp
#include <stdio.h    // C2013
```

Olası çözüm:

```
// C2013b.cpp
// compile with: /c
#include <stdio.h>
```