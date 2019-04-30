---
title: Derleyici Hatası C2040
ms.date: 11/04/2016
f1_keywords:
- C2040
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
ms.openlocfilehash: b45ec25f1ed516ae73b242fdcc7c66f68c92f724
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387116"
---
# <a name="compiler-error-c2040"></a>Derleyici Hatası C2040

'operator': 'ıdentifier1' farklıdır, 'identifier2' nden yöneltme düzeyi

Belirtilen işlenen içeren bir ifade, uyumsuz işlenen türleri vardır veya örtük olarak işlenen türleri dönüştürülür. Her iki işlenen de aritmetik veya her ikisi de (örneğin, dizi veya işaretçi) nonarithmetic, bunlar değişmeden kullanılır. Tek bir işlenen, aritmetik ve diğer değil, aritmetik işlenen nonarithmetic işlenen türüne dönüştürülür.

Bu örnek C2040 oluşturur ve bu sorunun nasıl gösterir.

```
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```