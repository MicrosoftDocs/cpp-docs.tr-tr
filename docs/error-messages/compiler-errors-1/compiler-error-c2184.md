---
title: Derleyici Hatası C2184
ms.date: 11/04/2016
f1_keywords:
- C2184
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
ms.openlocfilehash: 146035134cc159b9e4271ce10c94f196098581b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639978"
---
# <a name="compiler-error-c2184"></a>Derleyici Hatası C2184

'type': __except ifadesi için geçersiz tür, bir tamsayı olmalıdır

Bir tür kullanıldı bir [__except](../../c-language/try-except-statement-c.md) deyimi, ancak türüne izin verilmiyor.

Aşağıdaki örnek, C2184 oluşturur:

```
// C2184.cpp
void f() {
   int * p;
   __try{}
   __except(p){};   // C2184
}
```

Olası çözüm:

```
// C2184b.cpp
// compile with: /c
void f() {
   int i = 0;
   __try{}
   __except(i){};
}
```