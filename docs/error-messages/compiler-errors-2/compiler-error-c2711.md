---
title: Derleyici Hatası C2711
ms.date: 11/04/2016
f1_keywords:
- C2711
helpviewer_keywords:
- C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
ms.openlocfilehash: 568128d6199d16380b6a540173eded25f5588d23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160945"
---
# <a name="compiler-error-c2711"></a>Derleyici Hatası C2711

'function': Bu işlev yönetilen olarak derlenemiyor; #pragma unmanaged kullanmayı düşünün

Bazı yönergeleri, derleyici için kapsayan işlevin MSIL oluşturmasını engeller.

Aşağıdaki örnek, C2711 oluşturur:

```
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