---
title: Derleyici Hatası C2575
ms.date: 11/04/2016
f1_keywords:
- C2575
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
ms.openlocfilehash: 2737f9078e1c17358e3c975a5c3f8b6d211fd308
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434366"
---
# <a name="compiler-error-c2575"></a>Derleyici Hatası C2575

'identifier': yalnızca üye işlevler ve tabanlar sanal olabilir

Bir genel işlev veya sınıf bildirilen `virtual`. Buna izin verilmez.

Aşağıdaki örnek, C2575 oluşturur:

```
// C2575.cpp
// compile with: /c
virtual void func() {}   // C2575

void func2() {}
struct A {
   virtual void func2(){}
};
```