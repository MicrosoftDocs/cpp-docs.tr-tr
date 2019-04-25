---
title: Derleyici Hatası C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: 5ff8b0bee1f79d9534841e4368fd5a5249cbb413
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62153404"
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