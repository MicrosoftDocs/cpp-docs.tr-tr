---
title: Derleyici hatası C2162
ms.date: 11/04/2016
f1_keywords:
- C2162
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
ms.openlocfilehash: 4b4efd609aaa1f1c5bc50460ff653b36b12061e4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755700"
---
# <a name="compiler-error-c2162"></a>Derleyici hatası C2162

makro biçimsel parametresi bekleniyordu

Dize oluşturma işlecinden (#) sonraki belirteç bir biçimsel parametre adı değil.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2162 oluşturur:

```cpp
// C2162.cpp
// compile with: /c
#include <stdio.h>

#define print(a) printf_s(b)   // OK
#define print(a) printf_s(#b)    // C2162
```
