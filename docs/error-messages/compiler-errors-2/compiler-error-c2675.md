---
title: Derleyici Hatası C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: aea79509d0e1ae5c31fcf0cf369c28af39a21154
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499842"
---
# <a name="compiler-error-c2675"></a>Derleyici Hatası C2675

birli 'operator': 'type' bu işleci veya tanımlamıyor kabul edilebilir bir türe dönüştürme için önceden tanımlanmış işleç

C2675 birli işleç kullanılarak zaman da meydana gelebilir ve türü önceden tanımlanmış işleç için operatör ya da kabul edilebilir bir türe dönüştürmeyi tanımlamıyor. İşlecini kullanmak için belirtilen tür için aşırı veya tanımlar işlecin tanımlandığı bir türe dönüştürmeyi gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2675 oluşturur.

```
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```