---
title: Derleyici Hatası C3033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3033
dev_langs:
- C++
helpviewer_keywords:
- C3033
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61e1b1c4a5711b18263f22ce8344beb383eeafdb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051808"
---
# <a name="compiler-error-c3033"></a>Derleyici Hatası C3033

'var': 'yan tümcesi' yan tümcesindeki değişken const nitelenmiş türde olamaz

Belirli bir yan tümce için geçirilen değer olamaz `const` değişkenleri.

Aşağıdaki örnek, C3033 oluşturur:

```
// C3033.cpp
// compile with: /openmp /link vcomps.lib
int main() {
   const int val = 1;
   int val2 = 1;

   #pragma omp parallel reduction(+ : val)   // C3033
   ;

   #pragma omp parallel reduction(+ : val2)   // OK
   ;
}
```