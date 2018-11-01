---
title: Derleyici Hatası C2647
ms.date: 11/04/2016
f1_keywords:
- C2647
helpviewer_keywords:
- C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
ms.openlocfilehash: ac69dbb4de23be05d375126947fe003ef75fb85e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591873"
---
# <a name="compiler-error-c2647"></a>Derleyici Hatası C2647

'operator': 'type2' üzerinde 'type1' başvuramaz

Bir işaretçi-üye işlecinin sol işleneni ( `->*` veya `.*` ) doğru işlecine ilgili türüne örtük olarak dönüştürülemez.

Aşağıdaki örnek, C2647 oluşturur:

```
// C2647.cpp
class C {};
class D {};

int main() {
   D d, *pd;
   C c, *pc = 0;
   int C::*pmc = 0;
   pd->*pmc = 0;   // C2647
   d.*pmc = 0;   // C2647

   // OK
   pc->*pmc = 0;
   c.*pmc = 0;
}
```