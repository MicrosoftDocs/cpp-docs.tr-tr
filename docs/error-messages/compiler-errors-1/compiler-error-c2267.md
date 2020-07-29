---
title: Derleyici hatası C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: 0a72470feb79a226fe0f167364eeaea7dec9fd4d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87208479"
---
# <a name="compiler-error-c2267"></a>Derleyici hatası C2267

' function ': blok kapsamı olan statik işlevler geçersizdir

Yerel bir işlev bildirilmiştir **`static`** . Statik işlevlerin genel kapsamı olmalıdır.

Aşağıdaki örnek C2267 oluşturur:

```cpp
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```
