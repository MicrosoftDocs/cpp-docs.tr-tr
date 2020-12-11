---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2647'
title: Derleyici hatası C2647
ms.date: 11/04/2016
f1_keywords:
- C2647
helpviewer_keywords:
- C2647
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
ms.openlocfilehash: df434adde457ea9a3300291ec6fac2f49d806699
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160798"
---
# <a name="compiler-error-c2647"></a>Derleyici hatası C2647

' operator ': ' type2 ' üzerinde bir ' type1 ' başvurusu yapılamıyor

Bir işaretçiden üyeye işlecinin ( `->*` veya) sol işleneni `.*` örtük olarak sağ işleçle ilgili bir türe dönüştürülemez.

Aşağıdaki örnek C2647 oluşturur:

```cpp
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
