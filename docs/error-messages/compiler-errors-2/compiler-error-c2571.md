---
title: Derleyici Hatası C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: d7d4898e5f0b55c50a4c18cef053cc150394d7e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485078"
---
# <a name="compiler-error-c2571"></a>Derleyici Hatası C2571

'function': sanal işlevi, 'union' birleşimi içinde yer alamaz

UNION, bir sanal işlev ile bildirilir. Bir sınıf veya yapı içinde yalnızca bir sanal işlev bildirebilirsiniz.  Olası çözümler:

1. Bir sınıf veya yapı, birleşim değiştirin.

1. Sanal olmayan işlev olun.

Aşağıdaki örnek, C2571 oluşturur:

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```