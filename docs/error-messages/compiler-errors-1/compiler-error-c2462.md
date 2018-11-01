---
title: Derleyici Hatası C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: 0b342f8b878c48a77336fab4921cf4a668e248ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607060"
---
# <a name="compiler-error-c2462"></a>Derleyici Hatası C2462

'identifier': bir tür bir 'yeni-expression' içinde tanımlanamaz

İşlenen alanında bir tür tanımlanamaz `new` işleci. Tür tanımı içinde ayrı bir deyim koyun.

Aşağıdaki örnek, C2462 oluşturur:

```
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```