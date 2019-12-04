---
title: Derleyici hatası C3033
ms.date: 11/04/2016
f1_keywords:
- C3033
helpviewer_keywords:
- C3033
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
ms.openlocfilehash: 5d17f10e665a2c0ac86a10d90903e890b3c53386
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746402"
---
# <a name="compiler-error-c3033"></a>Derleyici hatası C3033

' var ': ' Clause ' yan tümcesindeki değişken const nitelenmiş türde olamaz

Belirli bir yan tümceciklere geçirilen değerler `const` değişken olamaz.

Aşağıdaki örnek C3033 oluşturur:

```cpp
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
