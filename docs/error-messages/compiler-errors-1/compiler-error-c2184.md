---
title: Derleyici hatası C2184
ms.date: 11/04/2016
f1_keywords:
- C2184
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
ms.openlocfilehash: 6c644bead9148c2019817b72f06587c36f3179c1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758456"
---
# <a name="compiler-error-c2184"></a>Derleyici hatası C2184

' Type ': __except ifadesi için geçersiz tür, tam sayı olmalıdır

Bir tür [__except](../../c-language/try-except-statement-c.md) ifadesinde kullanıldı, ancak türe izin verilmiyor.

Aşağıdaki örnek C2184 oluşturur:

```cpp
// C2184.cpp
void f() {
   int * p;
   __try{}
   __except(p){};   // C2184
}
```

Olası çözüm:

```cpp
// C2184b.cpp
// compile with: /c
void f() {
   int i = 0;
   __try{}
   __except(i){};
}
```
