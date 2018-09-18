---
title: Derleyici Hatası C2310 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2310
dev_langs:
- C++
helpviewer_keywords:
- C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2eed6dfc8d12b7bec9bb3437a3213b3feeda480e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099596"
---
# <a name="compiler-error-c2310"></a>Derleyici Hatası C2310

catch işleyicilerinin bir tür belirtmesi gerekir

Bir catch işleyicisi türü yok veya birden çok belirtilmiş.

Aşağıdaki örnek, C2310 oluşturur:

```
// C2310.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "Out of memory!";
   }
   catch( int ,int) {}   // C2310 two types
   // try the following line instead
   // catch( int)  {}
}
```