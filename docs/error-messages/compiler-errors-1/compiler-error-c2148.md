---
title: Derleyici hatası C2148
ms.date: 11/04/2016
f1_keywords:
- C2148
helpviewer_keywords:
- C2148
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
ms.openlocfilehash: aac14024e7ed2942eaf80c45817ba9c208e7e1ce
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756506"
---
# <a name="compiler-error-c2148"></a>Derleyici hatası C2148

dizinin toplam boyutu 0x7FFFFFFF baytı aşmamalıdır

Bir dizi sınırı aşıyor. Dizinin boyutunu küçültün.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2148 oluşturur:

```cpp
// C2148.cpp
#include <stdio.h>
#include <stdlib.h>

int main( ) {
   char MyArray[0x7ffffffff];   // C2148
   char * MyArray2 = (char *)malloc(0x7fffffff);

   if (MyArray2)
      printf_s("It worked!");
   else
      printf_s("It didn't work.");
}
```
