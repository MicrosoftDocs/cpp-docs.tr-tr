---
title: Derleyici hatası C2105
ms.date: 11/04/2016
f1_keywords:
- C2105
helpviewer_keywords:
- C2105
ms.assetid: 19b7f7bc-a9da-4d23-8193-005b6d09274f
ms.openlocfilehash: cbd09dda2b81bb34d395df6d8cdccb48b28c3025
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752216"
---
# <a name="compiler-error-c2105"></a>Derleyici hatası C2105

' operator ' için l-değeri gereklidir

İşlecin işlenen olarak bir l değeri olmalıdır.

Aşağıdaki örnek C2105 oluşturur:

```cpp
// C2105.cpp
int main() {
   unsigned char * p1 = 0;
   unsigned int * p2 = (unsigned int *)p1;
   p2++;

   unsigned int * p = 0;
   p++;   // ok

   p2 = (unsigned int *)p1;
   ((unsigned int *)p1)++;   // C2105
}
```

Aşağıdaki örnek C2105 oluşturur:

```cpp
// C2105b.cpp
int main() {
   int a[10] = {0};
   int b[10] = {0};
   ++(a , b);   // C2105

   // OK
   ++(a[0] , b[0]);
   ++a[0];
}
```
