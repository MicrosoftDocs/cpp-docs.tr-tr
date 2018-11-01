---
title: Derleyici Hatası C2050
ms.date: 11/04/2016
f1_keywords:
- C2050
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
ms.openlocfilehash: 99091452c2fc845ba396d7a8b290c2c857146257
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644869"
---
# <a name="compiler-error-c2050"></a>Derleyici Hatası C2050

switch ifadesi tamsayı değil

`switch` İfadeyi hesaplar için bir tamsayı değeri. Hatayı gidermek için in switch deyimleri yalnızca tamsayı değerlerini kullanın.

Aşağıdaki örnek, C2050 oluşturur:

```
// C2050.cpp
int main() {
   int a = 1;
   switch ("a") {   // C2050
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```

Olası çözüm:

```
// C2050b.cpp
int main() {
   int a = 1;
   switch (a) {
      case 1:
         a = 0;
      default:
         a = 2;
   }
}
```