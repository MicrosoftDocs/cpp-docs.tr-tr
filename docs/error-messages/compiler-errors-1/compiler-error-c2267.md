---
title: Derleyici Hatası C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: 5ff8b0bee1f79d9534841e4368fd5a5249cbb413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534855"
---
# <a name="compiler-error-c2267"></a>Derleyici Hatası C2267

'function': blok kapsamı olan statik işlevler geçersizdir

Yerel bir işlev bildirildiği `static`. Statik işlevler genel kapsamda olması gerekir.

Aşağıdaki örnek, C2267 oluşturur:

```
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```