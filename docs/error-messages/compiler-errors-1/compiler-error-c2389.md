---
title: Derleyici Hatası C2389
ms.date: 11/04/2016
f1_keywords:
- C2389
helpviewer_keywords:
- C2389
ms.assetid: 6122dc81-4ee3-49a5-a67d-d867808c9bac
ms.openlocfilehash: cb58ed0af3fda7ecbf399ac37758a688f014b826
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50664600"
---
# <a name="compiler-error-c2389"></a>Derleyici Hatası C2389

'operator': geçersiz işleç 'nullptr'

`nullptr` bir işlenen olamaz.

Aşağıdaki örnek, C2389 oluşturur:

```
// C2389.cpp
// compile with: /clr
int main() {
   throw nullptr;   // C2389
}
```