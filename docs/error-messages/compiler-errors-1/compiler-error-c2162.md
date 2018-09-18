---
title: Derleyici Hatası C2162 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2162
dev_langs:
- C++
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48d59ed5f0bf85befac0f8c462620a23faa08f98
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054005"
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