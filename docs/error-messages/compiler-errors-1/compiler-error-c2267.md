---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2267'
title: Derleyici hatası C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: df69073cbb1956033cf7d028c56e13018e4bbcf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328403"
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
