---
title: Derleyici hatası C2050
ms.date: 11/04/2016
f1_keywords:
- C2050
helpviewer_keywords:
- C2050
ms.assetid: 66aaed7d-00db-4ce1-a9d6-4447c1cf07ce
ms.openlocfilehash: e2eb6f323b5ae377c42bee4ad6ff8d83a1d3c16b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221308"
---
# <a name="compiler-error-c2050"></a>Derleyici hatası C2050

anahtar ifadesi tamsayı değil

**`switch`** İfade, tamsayı olmayan bir değer olarak değerlendirilir. Hatayı gidermek için Switch deyimlerinde yalnızca integral değerlerini kullanın.

Aşağıdaki örnek C2050 oluşturur:

```cpp
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

```cpp
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
