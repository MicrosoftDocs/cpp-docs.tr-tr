---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2040'
title: Derleyici hatası C2040
ms.date: 11/04/2016
f1_keywords:
- C2040
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
ms.openlocfilehash: 39e5152e012d793bcc174f5abe451e23f03b60d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175371"
---
# <a name="compiler-error-c2040"></a>Derleyici hatası C2040

' operator ': ' Identifier1 ', ' identifier2 ' öğesinden yöneltme seviyelerine göre farklılık gösterir

Belirtilen işlenenleri içeren bir ifade, uyumsuz işlenen türlerine veya örtük olarak dönüştürülmüş işlenen türlerine sahip. Her iki işlenen de aritmetik ise veya her ikisi de aritmetik değildir (dizi ya da işaretçi gibi), bunlar değişiklik olmadan kullanılır. Bir işlenen aritmetik ise ve diğeri değilse, aritmetik işlenen, aritmetik olmayan işlenenin türüne dönüştürülür.

Bu örnek C2040 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```
