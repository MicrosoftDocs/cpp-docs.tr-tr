---
title: Önemli hata C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: 99bfeea47ff46b6dadac9b32fa61306d54520d0f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747403"
---
# <a name="fatal-error-c1094"></a>Önemli hata C1094

'-Zmval1 ': komut satırı seçeneği önceden derlenmiş üstbilgiyi oluşturmak için kullanılan değerle tutarsız ('-Zmval2 ')

[/Rivc](../../build/reference/yc-create-precompiled-header-file.md) öğesine geçirilen değer, [/yu](../../build/reference/yu-use-precompiled-header-file.md) öğesine geçirilen değer olmalıdır ( **/ZM** değerleri, kullanan veya aynı önceden derlenmiş üst bilgi dosyasını oluşturan tüm derlemelerde aynı olmalıdır).

Aşağıdaki örnek C1094 oluşturur:

```
// C1094.h
int func1();
```

Ardından,

```cpp
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

Ardından,

```cpp
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```
