---
title: Derleyici Hatası C3037
ms.date: 11/04/2016
f1_keywords:
- C3037
helpviewer_keywords:
- C3037
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
ms.openlocfilehash: a022cfe6057f9ea518664090b5842faf4e822cb5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559971"
---
# <a name="compiler-error-c3037"></a>Derleyici Hatası C3037

'var': 'reduction' yan tümcesindeki değişken kapsayan bağlamda paylaşılabilir olmalıdır

Belirtilen bir değişken bir [azaltma](../../parallel/openmp/reference/reduction.md) yan tümcesi her iş parçacığının bağlamında özel olabilir.

Aşağıdaki örnek, C3037 oluşturur:

```
// C3037.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel private(g_i)
   // try the following line instead
   // #pragma omp parallel
   {
      #pragma omp for reduction(+:g_i)   // C3037
      for (i = 0 ; i < 10 ; ++i) {
         g_i += i;
      }
   }
}
```