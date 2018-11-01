---
title: Derleyici Hatası C2277
ms.date: 11/04/2016
f1_keywords:
- C2277
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
ms.openlocfilehash: 5b20594df8a250a54a0fd5902e0453f7438cbbfd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448093"
---
# <a name="compiler-error-c2277"></a>Derleyici Hatası C2277

'identifier': Bu üye işlevin adresi alınamaz

Bir üye işlevin adresi alınamaz.

Aşağıdaki örnek, C2277 oluşturur:

```
// C2277.cpp
class A {
public:
   A();
};
(*pctor)() = &A::A;   // C2277
```