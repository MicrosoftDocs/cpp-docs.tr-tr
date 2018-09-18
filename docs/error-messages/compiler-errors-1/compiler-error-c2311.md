---
title: Derleyici Hatası C2311 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2311
dev_langs:
- C++
helpviewer_keywords:
- C2311
ms.assetid: 1aff9bd5-ed0b-4db6-bbc0-01ac89850cf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f19e2a1b41c499605f22575f934b3d4872457011
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065107"
---
# <a name="compiler-error-c2311"></a>Derleyici Hatası C2311

'özel durum': satır numarasında '...' tarafından yakalandı

Üç nokta (...)'için catch işleyicisi bir throw son işleyicisi olmalıdır.

Aşağıdaki örnek, C2311 oluşturur:

```
// C2311.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "ooops!";
   }
   catch( ... ) {}
   catch( int ) {}   // C2311  ellipsis handler not last catch
}
```