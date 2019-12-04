---
title: Derleyici hatası C2711
ms.date: 11/04/2016
f1_keywords:
- C2711
helpviewer_keywords:
- C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
ms.openlocfilehash: 65612e4a7d19295a8fa49576fb1d72c852a76b82
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757442"
---
# <a name="compiler-error-c2711"></a>Derleyici hatası C2711

' function ': Bu işlev yönetilen olarak derlenemiyor, #pragma yönetilmeyen kullanmayı düşünün

Bazı yönergeler derleyicinin kapsayan işlev için MSIL üretmesine engel olur.

Aşağıdaki örnek C2711 oluşturur:

```cpp
// C2711.cpp
// compile with: /clr
// processor: x86
using namespace System;
value struct V {
   static const t = 10;
};

void bar() {
   V::t;
   __asm int 3   // C2711 inline asm can't be compiled managed
}
```
