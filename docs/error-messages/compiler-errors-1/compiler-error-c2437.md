---
title: Derleyici hatası C2437
ms.date: 11/04/2016
f1_keywords:
- C2437
helpviewer_keywords:
- C2437
ms.assetid: 2d2b3c6c-856a-4b27-ae10-64813b3e5483
ms.openlocfilehash: 745ab4f53223ec60e745068b1857206ed114086a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744348"
---
# <a name="compiler-error-c2437"></a>Derleyici hatası C2437

' tanımlayıcı ': zaten başlatılmış

Bir nesne yalnızca bir kez başlatılabilir.

Aşağıdaki örnek C2437 oluşturur:

```cpp
// C2437.cpp
// compile with: /c
class A {
public:
   A(int i) {}
};

class B : A {
   B() : A(1), A(2) {}   // C2437
   B() : A(1) {}   // OK
};
```
