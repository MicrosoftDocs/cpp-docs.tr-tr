---
description: 'Daha fazla bilgi edinin: önemli hata C1094'
title: Önemli hata C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: af83c6fa80a6e1b115146ad05513539fea7d348c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145099"
---
# <a name="fatal-error-c1094"></a>Önemli hata C1094

'-Zmval1 ': komut satırı seçeneği önceden derlenmiş üstbilgiyi oluşturmak için kullanılan değerle tutarsız ('-Zmval2 ')

[/Rivc](../../build/reference/yc-create-precompiled-header-file.md) öğesine geçirilen değer, [/yu](../../build/reference/yu-use-precompiled-header-file.md) öğesine geçirilen değer olmalıdır (**/ZM** değerleri, kullanan veya aynı önceden derlenmiş üst bilgi dosyasını oluşturan tüm derlemelerde aynı olmalıdır).

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
