---
title: Derleyici Hatası C2040 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2040
dev_langs:
- C++
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccfbacff97550e20c0dd0202e0737585ffd39d6d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016474"
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