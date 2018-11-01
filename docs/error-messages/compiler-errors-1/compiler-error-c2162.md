---
title: Derleyici Hatası C2162
ms.date: 11/04/2016
f1_keywords:
- C2162
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
ms.openlocfilehash: 02c0101324b28ebe548c38c6dc617faaa62315b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602412"
---
# <a name="compiler-error-c2162"></a>Derleyici Hatası C2162

Makro biçimsel parametresi bekleniyordu

Bir dize haline getirme işleci (#) aşağıdaki belirteç biçimsel parametre adı değil.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2162 oluşturur:

```
// C2162.cpp
// compile with: /c
#include <stdio.h>

#define print(a) printf_s(b)   // OK
#define print(a) printf_s(#b)    // C2162
```