---
title: Derleyici Hatası C2162
ms.date: 11/04/2016
f1_keywords:
- C2162
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
ms.openlocfilehash: 02c0101324b28ebe548c38c6dc617faaa62315b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174789"
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